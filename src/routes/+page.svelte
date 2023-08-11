<div class="grid md:grid-cols-3 gap-4 p-4">
    <div class="hero relative">
        <video autoplay loop muted class="video-bg">
            <source src="/vecteezy_retro-sci-fi-background-futuristic-grid-landscape-of-the-80s-digital-cyber-surface-suitable-for-design-in-the-style-of-the-1980s_1624138.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <img src="/ship.png" alt="Ship" class="ship">
        <img src="/invade.png" alt="Invader" class="invader"> <!-- Invader added here -->
        <div class="title">Your Title Here</div>
    </div>
    <!-- Rest of the grid items -->
    <!-- ... -->
</div>

<svg width="0" height="0" style="position:absolute">
    <linearGradient id="gradient" x1="0%" y1="0%" x2="0%" y2="100%">
        <stop offset="0%" style="stop-color:#a020f0; stop-opacity:1" />
        <stop offset="100%" style="stop-color:#32cd32; stop-opacity:1" />
    </linearGradient>
    <filter id="gradient-text">
        <feFlood flood-color="black" result="black" />
        <feFlood flood-color="red" result="color" />
        <feOffset in="SourceAlpha" dy="1" dx="1" result="offset" />
        <feComposite in="black" in2="offset" operator="in" result="comp" />
        <feComposite in="comp" in2="SourceAlpha" operator="in" />
        <feMerge>
            <feMergeNode in="SourceGraphic" />
            <feMergeNode in="comp" />
        </feMerge>
    </filter>
</svg>

<style lang="postcss">
    /* Custom Font */
    @font-face {
        font-family: 'PressStart2P';
        src: url('/fonts/PressStart2P-Regular.ttf') format('truetype');
        font-weight: normal;
        font-style: normal;
    }

    .grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 4px;
    }

    /* Hero */
    .hero {
        grid-column: span 3;
        position: relative;
        height: 90vh;
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

    /* Title Style */
    /* Title Style */
    .title {
    font-family: 'PressStart2P', sans-serif;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(1); /* Initial scale */
    font-size: 100%;
    z-index: 1;
    background: linear-gradient(to bottom, #a020f0, #32cd32);
    color: transparent;
    -webkit-background-clip: text;
    background-clip: text;
}

/* Breakpoints */
@media (max-width: 1800px) {
    .title {
        transform: translate(-50%, -50%) scale(4);
    }
}

@media (max-width: 992px) {
    .title {
        transform: translate(-50%, -50%) scale(2);
    }
}

@media (max-width: 768px) {
    .title {
        transform: translate(-50%, -50%) scale(.9);
    }
}

@media (max-width: 576px) {
    .title {
        transform: translate(-50%, -50%) scale(.5);
    }
}




    /* Ship Animation */
    .ship {
        animation: moveShip 3s alternate infinite;
        width: auto;
        height: 24%;
        position: absolute;
        bottom: 0;
        left: 0;
        --ship-width: -500%;
    }

    @keyframes moveShip {
        0% {
            transform: translateX(0);
        }
        100% {
            transform: translateX(calc(100% - var(--ship-width)));
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

    .invader {
    position: absolute;
    top: 0; /* Position at the top */
    left: 50%; /* Center horizontally */
    transform: translateX(-50%); /* Centering adjustment */
    width: auto;
    height: 24%; /* Adjust based on your needs */
    z-index: 1; /* Ensure it's above the video but below the title */
}
</style>
