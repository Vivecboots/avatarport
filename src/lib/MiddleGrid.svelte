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
        margin-top: 6%;
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
    <!-- First row: picture then card -->
    <div class="narrative-first">
        <img src="/mountain.png" alt="Giant Phone">
    </div>
    <div class="skeleton-card-first">
        In the digital frontier, the valuation of cryptocurrencies, now eclipsing 1 trillion USD, is merely a chapter in a broader story. Blockchain technology's strength lies in its unparalleled ability to safeguard identity and manage intricate state changes in a world where digital replication is all too easy. As we advance technology, the need for robust verification intensifies.

Web3, with its market dynamics, is undeniably the blueprint for our digital future. Past underestimations, like those concerning home computers, emphasize the significance of early immersion in transformative technologies.

At the heart of my Web3 commitment are the principles of ownership, privacy, and equality. I champion interoperability that's both seamless and cost-effective. A fair fee structure, irrespective of scale or arbitrary uses, is vital to ensure that everyone, regardless of socio-economic status, can participate equitably.
    </div>

    <!-- Second row: card then picture -->
    <div class="skeleton-card-second">
        My proficiency in Typescript and Javascript isn't just about coding. It's a testament to the profound ripple effects that individual decisions in tech can create. Investing my energy and expertise in blockchain now means I'm not only shaping its present but also influencing its future trajectory. The choices made today in this space could have far-reaching impacts, potentially shaping facets of humanity in ways we might not yet fully grasp.

Financial realms, from traditional stock markets to emerging crypto spaces, always attract a blend of visionaries and opportunists. While stock markets have evolved into esteemed institutions, the crypto world is on a similar journey of maturation. I'm eager to be part of this transformative path, contributing to its refinement and potential.

 who made a small decision one day to name a function if.  And that if changed everything.  And thats what led me here, one question about what I stand for as a person, if, if this is what I believe in, then what are the consequences  if I don’t do it. I hope to work with only teams that feel the same passion.  Finances attract scammers, certainly.  But the stock financial sector doesnt let it define it  Rather, they are prestigious.  And one day, as the younger generations grow into the role, so will the new technology.  
    </div>
    <div class="narrative-second">
        <img src="/SantaMonica.png" alt="Mountain">
    </div>
</div>
