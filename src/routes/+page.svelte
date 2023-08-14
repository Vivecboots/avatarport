<div class="grid md:grid-cols-3 gap-4 p-4">
    <div class="hero relative">
        <video autoplay loop muted class="video-bg">
            <source src="/vecteezy_retro-sci-fi-background-futuristic-grid-landscape-of-the-80s-digital-cyber-surface-suitable-for-design-in-the-style-of-the-1980s_1624138.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        
        <img src="/ship.png" alt="Ship" class="ship">
        <img src="/invade.png" alt="Invader" class="invader" id="invaderImg">
        <div class="score">Score: <span id="scoreCounter">0</span></div>

        <div class="title"><span>Blair Winslow-Nason</span></div>
    </div>
    <div class="full-width-grid">
        
        <MiddleGrid />
        
    </div>
    

    
<div>
   
</div>
          
    <div class="stepper-container">
        <div class="progress-bar"></div>
        <div class="steps">
            <div class="step active">
                <div class="step-header">Step 1: Introduction</div>
                <div class="step-content">
                    <DancingFigure />
                </div>
            </div>
            <!-- Add more steps as needed -->
            <div class="step step-2">
                <div class="step-header">Step 2</div>
                <div class="step-content">
                    <!-- Content for Step 2 -->
                </div>
            </div>
            <!-- ... up to Step 6 ... -->
        </div>
        <div class="step-navigation">
            <button class="back-btn">Back</button>
            <button class="next-btn">Next</button>
        </div>
    </div>
    <!-- ... rest of the grid items ... -->
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

<audio id="invaderSound" src="/mixkit-arcade-slot-machine-wheel-1933.wav"></audio>
<audio id="shipSound" src="/laser.mp3"></audio>
<audio id="titleSound" src="/music_zapsplat_game_music_arcade_electro_repeating_retro_arp_electro_drums_serious_012.mp3"></audio>


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
    gap: 0px;
}

/* Hero */
.hero {
    grid-column: span 3;
    position: relative;
    height: 90vh;
    box-shadow: 0 0 50px #9e2eff; /* Neon green shadow at minimum glow */
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
.title {
    font-family: 'PressStart2P', sans-serif;
    position: relative;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(1);
    font-size: 100%;
    z-index: 1;
    display: inline-block;
}

.title span {
    background: linear-gradient(to bottom, #a020f0, #32cd32);
    color: transparent;
    -webkit-background-clip: text;
    background-clip: text;
    display: block;
    transition: opacity 0.3s; /* Transition only the opacity */
    opacity: 1; /* Default opacity */
}

.title::before {
    content: "DeFi and Web3 Dev";
    position: absolute;
    top: 0;
    left: 1rem;
    width: 100%;
    height: 100%;
    background: linear-gradient(to bottom, lime, lime); /* Set both gradient stops to lime for a solid neon lime green color */
    color: transparent;
    -webkit-background-clip: text;
    background-clip: text;
    text-shadow: 0 0 5px lime, 0 0 10px lime, 0 0 15px lime, 0 0 20px lime; /* neon glow */

    opacity: 0;
    visibility: hidden;
    transition: opacity 0.3s, visibility 0.3s;
}

.title:hover span {
    opacity: 0;
}

.title:hover::before {
    opacity: 1;
    visibility: visible;
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
    --ship-width: -450%;
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
    top: 0;
    left: 0;
    width: auto;
    height: 24%;
    z-index: 2;
    animation: moveInvader 3s alternate infinite;
    --invader-width: -300%;
}

@keyframes moveInvader {
    0%, 100% {
        transform: translateX(0);
    }
    50% {
        transform: translateX(calc(50% - var(--invader-width)));
    }
}


.score {
    font-family: 'PressStart2P', sans-serif;
    position: absolute;
    top: 10px;
    left: 10px;
    font-size: 1.5rem;
    color: white;
    z-index: 3;
    background-color: rgba(0, 0, 0, 0.5);
    padding: 10px;
    border-radius: 5px;
}

.dancing-figure {
   
    z-index: 100; 
}



.stepper-container {
    grid-column: span 3; 
    display: flex;
    flex-direction: column;
    gap: 24px;
    max-height: 100vh; /* Set a maximum height */
    overflow-y: auto; /* Make it scrollable vertically */
    width: 97%;
    border: 3px solid black; /* Thicker black outline */
    padding: 16px;
    border-radius: 0; /* Square edges */
    background: linear-gradient(to bottom, #3b3d91, #a020f0); /* Gradient background from blue to purple */
    margin-top: 6%;
    overflow-x: hidden;
    top: 50%; 
}





.progress-bar {
    height: 10px;
    background: #e0e0e0;
    border-radius: 5px;
    position: relative;
    margin-bottom: 16px;
}

.step {
    padding: 16px;
    border-radius: 10px;
    background-color: #0000FF; /* Blue color */
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    margin-bottom: 16px;
}

.step {
    padding: 16px;
    border-radius: 10px;
    background-color: white;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    margin-bottom: 16px;
}

.step.active {
    border: 2px solid #8a41df;
}

.step-header {
    font-weight: bold;
    margin-bottom: 8px;
}

.step-content {
    margin-bottom: 8px;
}

.step-navigation {
    display: flex;
    justify-content: space-between;
}

.back-btn, .next-btn {
    padding: 10px 20px;
    border: 3px solid black; /* Thicker black outline */
    background: #39FF14; /* Neon green background */
    color: black; /* Black text color */
    cursor: pointer;
    box-shadow: 0px 0px 10px #39FF14; /* Neon green shadow */
    transition: transform 0.2s, background-color 0.2s; /* Smooth transition for hover effect and background color change */
}

.back-btn:hover, .next-btn:hover {
    background-color: rgb(255, 111, 59); /* Neon orange background on hover */
    transform: scale(1.05); /* Slightly enlarge the button on hover */
    cursor: pointer; /* Hand icon on hover */
}

.back-btn:disabled, .next-btn:disabled {
    background: #e0e0e0;
    cursor: not-allowed;
    box-shadow: none; /* Remove shadow for disabled state */
}



.step-2 {
    background-color: #0000FF; /* Blue color for testing */
}

/* Specific styles for Step 1 and Step 2 */
.step:nth-child(1), .step:nth-child(2) {
    background-color: black;
}

/* Gradient background for the stepper container */
.stepper-container {
    background: linear-gradient(to bottom, #3b3d91, #a020f0); /* Gradient from blue to purple */
    position: relative;
    /* ... other existing styles ... */
}


.stepper-container::-webkit-scrollbar {
    width: 12px; /* Adjust width as needed */
}

.stepper-container::-webkit-scrollbar-track {
    background: #f0f0f0; /* Adjust color as needed */
}

/* Style for the scrollbar thumb */
.stepper-container::-webkit-scrollbar-thumb {
    background-color: rgb(255, 111, 59); /* Neon orange color */
    border-radius: 6px; /* Adjust as needed */
}

.stepper-container::-webkit-scrollbar-thumb:hover {
    background-color: #d97a4f; /* Slightly darker shade of orange for hover effect */
    padding-right: 4%;
}

.full-width-grid {
    grid-column: span 3;
    display: flex;
    flex-direction: column;
}



</style>


<script>
import DancingFigure from '../lib/DancingFigure.svelte';
import { onMount } from 'svelte';
import MiddleGrid from '../lib/MiddleGrid.svelte';
import SecondMiddleGrid from '../lib/SecondMiddleGrid.svelte';

onMount(() => {
    const invaderImg = document.getElementById('invaderImg');
    const shipImg = document.querySelector('.ship');
    const invaderSound = document.getElementById('invaderSound');
    const shipSound = document.getElementById('shipSound');
    const titleSound = document.getElementById('titleSound');
    const titleElement = document.querySelector('.title');
    const scoreCounter = document.getElementById('scoreCounter');
    let score = 0;

    invaderImg.addEventListener('click', function() {
        invaderSound.play();
        score += 1;
        scoreCounter.textContent = score;
    });

    shipImg.addEventListener('click', function() {
        shipSound.play();
        score += 2;
        scoreCounter.textContent = score;
    });

    titleElement.addEventListener('click', function() {
        titleSound.play();
    });

    invaderImg.addEventListener('mouseover', function() {
        invaderImg.src = '/greeninvader.png';
    });

    invaderImg.addEventListener('mouseout', function() {
        invaderImg.src = '/invade.png';
    });

    // Stepper functionality
let currentStep = 0;
const steps = document.querySelectorAll('.step');
const progressBar = document.querySelector('.progress-bar::before');
const nextBtn = document.querySelector('.next-btn');
const backBtn = document.querySelector('.back-btn');

function updateStep() {
    steps.forEach((step, index) => {
        if (index === currentStep) {
            step.classList.add('active');
        } else {
            step.classList.remove('active');
        }
    });
    progressBar.style.width = `${(currentStep / (steps.length - 1)) * 100}%`;
}

nextBtn.addEventListener('click', function() {
    if (currentStep < steps.length - 1) {
        currentStep++;
        updateStep();
    }
});

backBtn.addEventListener('click', function() {
    if (currentStep > 0) {
        currentStep--;
        updateStep();
    }
});


});

</script>


