<div class="grid md:grid-cols-3 gap-4 p-4">
    <div class="hero relative">
        <video autoplay loop muted class="video-bg">
            <source src="/vecteezy_retro-sci-fi-background-futuristic-grid-landscape-of-the-80s-digital-cyber-surface-suitable-for-design-in-the-style-of-the-1980s_1624138.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <img src="/ship.png" alt="Ship" class="ship">
    </div>
    <div class="grid-item bg-blue-500">2</div>
    <div class="grid-item bg-green-500">3</div>
    <div class="grid-item bg-yellow-500">4</div>
    <div class="grid-item bg-purple-500">5</div>
    <div class="grid-item bg-indigo-500">6</div>
    <div class="grid-item bg-pink-500">7</div>
    <div class="grid-item bg-teal-500">8</div>
    <div class="grid-item bg-orange-500">9</div>
</div>

<style lang="postcss">
    .grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 4px;
    }

    /* Hero */
    .hero {
        grid-column: span 3;
        position: relative;
        height: 66.66vh; /* Adjust this value as needed */
    }

    .video-bg {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        z-index: -1;
    }

    /* Ship Animation */
    .ship {
        animation: moveShip 3s alternate infinite;
        width: auto; /* Adjust based on your needs */
        height: 10%; /* Adjust based on your needs */
		
    }

 @keyframes moveShip {
        0% {
            transform: translateX(0);
        }
        100% {
            transform: translateX(calc(100% - 100px)); /* Adjust this value based on the width of the ship image */
        }
    }

    /* Square grid items */
    .grid-item {
        aspect-ratio: 1 / 1;
    }

    /* Existing styles */
    figure {
        @apply flex relative flex-col;
    }
    figure svg,
    .img-bg {
        @apply w-64 h-64 md:w-80 md:h-80;
    }
    .img-bg {
        @apply absolute z-[-1] rounded-full blur-[50px] transition-all;
        animation: pulse 5s cubic-bezier(0, 0, 0, 0.5) infinite,
            glow 5s linear infinite;
    }
    @keyframes glow {
        0% {
            @apply bg-primary-400/50;
        }
        33% {
            @apply bg-secondary-400/50;
        }
        66% {
            @apply bg-tertiary-400/50;
        }
        100% {
            @apply bg-primary-400/50;
        }
    }
    @keyframes pulse {
        50% {
            transform: scale(1.5);
        }
    }
</style>
