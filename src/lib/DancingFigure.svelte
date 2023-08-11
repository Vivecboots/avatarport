<script>
    import { onMount } from 'svelte';
    import * as THREE from 'three';
    import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js';

    let figureContainer;

    onMount(() => {
        const scene = new THREE.Scene();

        // Add ambient and directional light
        const ambientLight = new THREE.AmbientLight(0xffffff, 0.5);
        scene.add(ambientLight);

        const directionalLight = new THREE.DirectionalLight(0xffffff, 1);
        directionalLight.position.set(0, 1, 0);
        scene.add(directionalLight);

        const camera = new THREE.PerspectiveCamera(75, figureContainer.clientWidth / figureContainer.clientHeight, 0.1, 1000);
        camera.position.z = 5; // Adjust this value as needed

        const renderer = new THREE.WebGLRenderer({ antialias: true });
        renderer.setSize(figureContainer.clientWidth, figureContainer.clientHeight);
        figureContainer.appendChild(renderer.domElement);

        const loader = new GLTFLoader();
        loader.load(
            '/checkwatch.glb',
            (gltf) => {
                scene.add(gltf.scene);
            },
            undefined, // For progress callback (if needed)
            (error) => {
                console.error("An error occurred while loading the GLTF model:", error);
            }
        );

        const animate = () => {
            requestAnimationFrame(animate);
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
