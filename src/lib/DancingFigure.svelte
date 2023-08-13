<script>
    import { onMount } from 'svelte';
    import * as THREE from 'three';
    import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js';
    import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js';

    let figureContainer;
    let mixer;
    let defaultAction, backflipAction;

    onMount(() => {
        const scene = setupScene();
        const camera = setupCamera();
        const renderer = setupRenderer();
        const controls = setupControls(camera, renderer);
        setBackground(renderer);
        loadModels(scene);

        figureContainer.addEventListener('click', handleFigureClick);

        animate(scene, camera, renderer, controls);
    });

    function setupScene() {
    const scene = new THREE.Scene();

    // Lights
    const ambientLight = new THREE.AmbientLight(0xffffff, 0.5);
    scene.add(ambientLight);

    const directionalLight = new THREE.DirectionalLight(0xffffff, 1);
    directionalLight.position.set(0, 1, 1).normalize();
    scene.add(directionalLight);

    // Skybox
    const textureLoader = new THREE.TextureLoader();
    const bgTexture = textureLoader.load('/between_bridges_4k.png');
    const skyboxGeometry = new THREE.SphereGeometry(500, 60, 40);
    const skyboxMaterial = new THREE.MeshBasicMaterial({ map: bgTexture, side: THREE.BackSide });
    const skybox = new THREE.Mesh(skyboxGeometry, skyboxMaterial);
    scene.add(skybox);

    return scene;
}


    function setupCamera() {
        const camera = new THREE.PerspectiveCamera(75, figureContainer.clientWidth / figureContainer.clientHeight, 0.1, 1000);
        camera.position.z = 5;
        return camera;
    }

    function setupRenderer() {
        const renderer = new THREE.WebGLRenderer({ alpha: true });
        renderer.setClearColor(0x000000, 0);
        renderer.setSize(figureContainer.clientWidth, figureContainer.clientHeight);
        figureContainer.appendChild(renderer.domElement);
        return renderer;
    }

    function setupControls(camera, renderer) {
    const controls = new OrbitControls(camera, renderer.domElement);
    
    controls.minDistance = 2; // Adjust this value based on your needs
    controls.maxDistance = camera.position.z * 5;
    controls.zoomSpeed = 0.5;
    
    // Restrict vertical orbit to top half
    controls.minPolarAngle = 0; // Top
    controls.maxPolarAngle = Math.PI / 2; // Horizontal

    return controls;
}



    function setBackground(renderer) {
        const textureLoader = new THREE.TextureLoader();
        const bgTexture = textureLoader.load('/city-7091684_1280.jpg');
        renderer.background = bgTexture;
    }

    function loadModels(scene) {
    const loader = new GLTFLoader();
    loader.load('/checkwatch.glb', (gltf) => {
        gltf.scene.scale.set(0.88, 0.88, 0.88);
        gltf.scene.position.y = -1;  // Adjust this value to position the character further up or down
        gltf.scene.position.z = 3;  // Adjust this value to move the character forward or backward
        scene.add(gltf.scene);

        if (gltf.animations && gltf.animations.length) {
            mixer = new THREE.AnimationMixer(gltf.scene);
            defaultAction = mixer.clipAction(gltf.animations[0]);
            defaultAction.play();

            loader.load('/backflip.glb', (backflipGltf) => {
                if (backflipGltf.animations && backflipGltf.animations.length) {
                    backflipAction = mixer.clipAction(backflipGltf.animations[0]);
                }
            });
        }
    });
}



    function handleFigureClick() {
        if (mixer && backflipAction) {
            mixer.stopAllAction();
            backflipAction.reset().setLoop(THREE.LoopOnce).play();

            setTimeout(() => {
                defaultAction.reset().play();
            }, 1300);
        }
    }

    function animate(scene, camera, renderer, controls) {
        const render = () => {
            requestAnimationFrame(render);
            if (mixer) {
                mixer.update(0.01);
            }
            controls.update();
            renderer.render(scene, camera);
        };
        render();
    }
</script>

<div bind:this={figureContainer} class="figure-container col-span-2">
    <div id="3d-figure"></div>
</div>

<style>
    .figure-container {
        height: 55.66vh;
        position: relative;
    }

    #3d-figure {
        width: 100%;
        height: 100%;
    }
</style>
