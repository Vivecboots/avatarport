<script>
    import { onMount } from 'svelte';
    import * as THREE from 'three';
    import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js';

    let figureContainer;

    onMount(() => {
        const scene = new THREE.Scene();

        // Lights
        const ambientLight = new THREE.AmbientLight(0xffffff, 0.5); // Soft white light
        scene.add(ambientLight);

        const directionalLight = new THREE.DirectionalLight(0xffffff, 1);
        directionalLight.position.set(0, 1, 1).normalize();
        scene.add(directionalLight);

        const camera = new THREE.PerspectiveCamera(75, figureContainer.clientWidth / figureContainer.clientHeight, 0.1, 1000);
        camera.position.z = 5;

        const renderer = new THREE.WebGLRenderer({ alpha: true });
        renderer.setClearColor(0x000000, 0); // Set clear color to black with full transparency
        renderer.setSize(figureContainer.clientWidth, figureContainer.clientHeight);
        figureContainer.appendChild(renderer.domElement);

        let mixer; // Declare the mixer for animations

        const loader = new GLTFLoader();
        loader.load(
            '/checkwatch.glb',
            (gltf) => {
                scene.add(gltf.scene);

                // If there are animations, play them
                if (gltf.animations && gltf.animations.length) {
                    mixer = new THREE.AnimationMixer(gltf.scene);
                    gltf.animations.forEach((clip) => {
                        mixer.clipAction(clip).play();
                    });
                }
            },
            undefined,
            (error) => {
                console.error("An error occurred while loading the GLTF model:", error);
            }
        );

        const animate = () => {
            requestAnimationFrame(animate);

            // Update the mixer on each frame
            if (mixer) {
                mixer.update(0.01); // You can adjust this value for animation speed
            }

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
        height: 75vh;
        position: relative;
    }

    #3d-figure {
        width: 100%;
        height: 100%;
    }
</style>
