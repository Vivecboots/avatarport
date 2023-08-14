<style>
    .grid-container {
        padding-left: 6%; /* 6% padding on the left */
        padding-right: 6%; /* 6% padding on the right */
        display: grid;
        grid-template-columns: repeat(6, 1fr);
        gap: 16px;
        width: 88vw; /* Adjusted for the 6% padding on both sides */
        height: 23vh;
        margin-top: 6%;
        margin-bottom: 10%;
    }

    .narrative-first {
        grid-column: 1/3;
        background: url('/mountain.png') no-repeat center center;
        background-size: contain;
        height: auto;
        margin-right: 20%;
    }

    .skeleton-card-first {
        grid-column: 4/7;
        padding: 20px;
        border: 1px solid #e0e0e0;
        border-radius: 8px;
        color: #010101;
        margin-right: 10%;
    }

    .narrative-second {
        grid-column: 4/7;
        background: url('/mountain.png') no-repeat center center;
        background-size: contain;
        height: auto;
        margin-left: 20%;
    }

    .skeleton-card-second {
        grid-column: 1/4;
        padding: 20px;
        border: 1px solid #e0e0e0;
        border-radius: 8px;
        color: #010101;
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
    <div class="narrative-first"></div>
    <div class="skeleton-card-first">
        In an evolving digital realm, where identities are effortlessly crafted, the true challenge lies in authenticating ownership and identity. As a detail-oriented problem solver with a focus on blockchain technology, I've delved deep into the world of crypto, not just as a currency but as a tool for ensuring security and preserving anonymity. With expertise in Java, Svelte, EVM, Zero-Knowledge EVM, Solidity, and Web3, I've been at the forefront of projects that bridge real-life with the digital, especially focusing on inter-chain interoperability. My work with Yiddishland, developing efficient web infrastructures, and my training as a Full-Stack Developer, has equipped me to understand and address the challenges of digital ownership in an AI-driven world. Believing in the potential of blockchain beyond finance, I'm passionate about shaping a future where technology stabilizes our world, ensuring fairness and equity for all
    </div>

    <!-- Second row: card then picture -->
    <div class="skeleton-card-second">
        In an evolving digital realm, where identities are effortlessly crafted, the true challenge lies in authenticating ownership and identity. As a detail-oriented problem solver with a focus on blockchain technology, I've delved deep into the world of crypto, not just as a currency but as a tool for ensuring security and preserving anonymity. With expertise in Java, Svelte, EVM, Zero-Knowledge EVM, Solidity, and Web3, I've been at the forefront of projects that bridge real-life with the digital, especially focusing on inter-chain interoperability. My work with Yiddishland, developing efficient web infrastructures, and my training as a Full-Stack Developer, has equipped me to understand and address the challenges of digital ownership in an AI-driven world. Believing in the potential of blockchain beyond finance, I'm passionate about shaping a future where technology stabilizes our world, ensuring fairness and equity for all
    </div>
    <div class="narrative-second"></div>
</div>
