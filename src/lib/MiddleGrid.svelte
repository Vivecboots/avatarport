<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap">


<style>
    @keyframes glowing {
        0%, 100% {
            box-shadow: 0 0 15px #32CD32; /* Neon green shadow at minimum glow */
        }
        50% {
            box-shadow: 0 0 40px #32CD32, 0 0 30px #32CD32; /* Neon green shadow at maximum glow */
        }
    }

    .grid-container {
        padding-left: 2%;
        padding-right: 2%;
        display: grid;
        grid-template-columns: repeat(12, 1fr); /* 12 columns */
        gap: 40% 16px; /* 7% vertical gap between rows and 16px horizontal gap between columns */
        width: 100%;
        height: 23vh;
        margin-top: 16%;
        margin-bottom: 10%;
    }

  

    .narrative-first, .narrative-second {
        background-size: 35%; /* Scale the image to 35% of the container's size */
        background-position: center; /* Center the image within its container */
        height: 300px; /* Set a fixed height for the container */
    }

    


    .narrative-first {
        grid-column: 1/4; /* Picture takes 3 columns */
       
    }

    .narrative-second {
        grid-column: 10/13; /* Picture takes 3 columns */
        
    }

    .skeleton-card-first, .skeleton-card-second {
        padding: 20px;
        border: 0px solid #9400D3; /* Neon purple border */
        border-radius: 8px;
        color: #010101;
        animation: glowing 5s infinite; /* Apply the glowing effect */
        font-family: 'Press Start 2P', cursive;
    }

   
    
    .skeleton-card-first {
        grid-column: 4/13; /* Adjusted to span 9 columns */
    }

    .skeleton-card-second {
        grid-column: 1/10; /* Remains the same, spanning 9 columns */
    }


    @media (max-width: 768px) {
        .grid-container {
            grid-template-columns: 1fr;
            gap: 8px;
        }

        .narrative-first, .skeleton-card-first, .narrative-second, .skeleton-card-second {
            grid-column: 1 / -1;
            margin-right: 0;
            margin-left: 0;
        }
    }
</style>



<div class="grid-container">
    <div class="narrative-first">
        <img src="/mountain.png" alt="Giant Phone">
    </div>
    <div class="skeleton-card-first">
        In the realm of digital innovation, the monumental rise of cryptocurrencies, now valued over 1 trillion USD, is just one chapter in a broader narrative. The essence of blockchain technology isn't merely its financial implications but its unparalleled ability to secure identities and manage intricate digital interactions in an age where duplication is effortless. As we push the boundaries of technology, the urgency for robust verification becomes paramount. Web3, with its intricate market dynamics, is undeniably the cornerstone of our digital future.

        Reflecting on the history of technology, I'm reminded of the foundational decisions made in the development of JavaScript. One individual's seemingly simple choices, like naming a function "if," have since become integral to the lexicon of countless developers. These decisions, though seemingly minute at the time, have shaped the digital world we navigate today. Hundreds of thousands, if not millions, of developers have internalized and built upon these foundational choices, leading to the creation of digital societies and ecosystems.
    </div>

    <div class="skeleton-card-second">
        Similarly, as we stand on the precipice of blockchain's potential, I recognize that the decisions we make now, no matter how small, can have a ripple effect, shaping the future of finance and digital interactions. My expertise in JavaScript isn't just a testament to my coding skills but symbolizes the profound impact that individual choices can have on a global scale. By immersing myself in blockchain, I'm not just participating in its present but actively sculpting its future trajectory.

        The financial world, both traditional stock markets and the burgeoning crypto space, attracts a mix of visionaries and opportunists. While stock markets have matured into esteemed institutions, I believe the crypto realm, with the right guidance and decisions, is on a similar evolutionary path. I'm eager to be part of this transformative journey, ensuring that the legacy we leave behind is as impactful as the foundational decisions made in the early days of JavaScript.
    </div>
    <div class="narrative-second">
        <img src="/SantaMonica.png" alt="Mountain">
    </div>
</div>
