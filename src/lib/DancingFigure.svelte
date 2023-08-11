<script>
    import { onMount } from 'svelte';
    import * as THREE from 'three';
    import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js';
    import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js';

    let figureContainer;

    onMount(() => {
        const scene = new THREE.Scene();

        // Lights
        const ambientLight = new THREE.AmbientLight(0xffffff, 0.5);
        scene.add(ambientLight);

        const directionalLight = new THREE.DirectionalLight(0xffffff, 1);
        directionalLight.position.set(0, 1, 1).normalize();
        scene.add(directionalLight);

        const camera = new THREE.PerspectiveCamera(75, figureContainer.clientWidth / figureContainer.clientHeight, 0.1, 1000);
        camera.position.z = 5;

        const renderer = new THREE.WebGLRenderer({ alpha: true });
        renderer.setClearColor(0x000000, 0);
        renderer.setSize(figureContainer.clientWidth, figureContainer.clientHeight);
        figureContainer.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera, renderer.domElement);
        controls.minDistance = camera.position.z / 2.5;
        controls.maxDistance = camera.position.z * 2.5;

        let mixer;
        let defaultAction;
        let backflipAction;

        const loader = new GLTFLoader();

        // Load the default model and animation
        loader.load(
            '/checkwatch.glb',
            (gltf) => {
                scene.add(gltf.scene);

                mixer = new THREE.AnimationMixer(gltf.scene);
                defaultAction = mixer.clipAction(gltf.animations[0]);
                defaultAction.play();

                // Load the backflip animation
                loader.load('/backflip.glb', (gltfBackflip) => {
                    backflipAction = mixer.clipAction(gltfBackflip.animations[0]);
                });
            }
        );

        figureContainer.addEventListener('click', () => {
            if (mixer && backflipAction) {
                mixer.stopAllAction();
                backflipAction.setLoop(THREE.LoopOnce);
                backflipAction.play();

                backflipAction.addEventListener('finished', () => {
                    mixer.stopAllAction();
                    defaultAction.play();
                });
            }
        });

        const animate = () => {
            requestAnimationFrame(animate);

            if (mixer) {
                mixer.update(0.01);
            }

            controls.update();
            renderer.render(scene, camera);
        };

        animate();
    });
</script>

<div bind:this={figureContainer} class="figure-container col-span-2">
    <div id="3d-figure"></div>
</div>

<style>
    .figure-container {
        height: 250vh;
        position: relative;
    }

    #3d-figure {
        width: 100%;
        height: 100%;
    }
</style>
