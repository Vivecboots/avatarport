<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-modern.css';
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
	import { onMount } from 'svelte';

	onMount(() => {
	    // Hide the loading screen after a delay (e.g., 3 seconds)
	    setTimeout(() => {
	        const loadingScreen = document.getElementById('loadingScreen');
	        loadingScreen.style.display = 'none';
	    }, 3000);
	});
</script>

<!-- App Shell -->
<AppShell>
    <!-- Loading Screen -->
    <div id="loadingScreen" class="fixed inset-0 z-50 flex items-center justify-center">
        <video autoplay loop muted class="loading-video">
            <source src="/vecteezy_cyberpunk-retro-arcade-machine-game-pixel-art-animation_23026017_331.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
    </div>

    <svelte:fragment slot="header">
        <!-- App Bar -->
        <AppBar>
            <svelte:fragment slot="lead">
                <strong class="text-xl uppercase">Blair Winslow-Nason: Web3, DeFi and Full-Stack Dev</strong>
            </svelte:fragment>
            <svelte:fragment slot="trail">
                <a
                    class="btn btn-sm variant-ghost-surface"
                    href="https://docs.google.com/document/d/1_m-KOzEDbvb9CMK1_dTkZWr02DnQV81q93sZspQhWUw/edit?usp=sharing"
                    target="_blank"
                    rel="noreferrer"
                >
                    Resume
                </a>
              
                <a
                    class="btn btn-sm variant-ghost-surface"
                    href="https://github.com/Vivecboots"
                    target="_blank"
                    rel="noreferrer"
                >
                    GitHub
                </a>
            </svelte:fragment>
        </AppBar>
    </svelte:fragment>
    <!-- Page Route Content -->
    <slot />
</AppShell>

<style>
#loadingScreen {
    background-color: rgba(0, 0, 0, 0.8); /* Semi-transparent black background */
}

.loading-video {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
</style>
