<style>
    .grid-container {
        padding-left: 10%;
        display: grid;
        grid-template-columns: repeat(6, 1fr);
        gap: 16px;
        width: 100vw;
        height: 23vh;
        margin-top: 6%;
        margin-bottom: 10%;
    }

    .narrative {
        grid-column: 1/3;
        background: url('/midinghtgame.gif') no-repeat center center;
        background-size: contain;
        height: auto;
        margin-right: 20%;
    }

    .skeleton-card {
        grid-column: 4/7;
        padding: 20px;
        border: 1px solid #e0e0e0;
        border-radius: 8px;
        color: #010101;
        margin-right: 10%;
    }

    @media (max-width: 768px) {
        .grid-container {
            grid-template-columns: 1fr;
            gap: 8px;
        }

        .narrative, .skeleton-card {
            grid-column: 1 / -1;
        }
    }
</style>

<div class="grid-container">
    <div class="narrative"></div>
    <div class="skeleton-card">
        In an evolving digital realm, where identities are effortlessly crafted, the true challenge lies in authenticating ownership and identity. As a detail-oriented problem solver with a focus on blockchain technology, I've delved deep into the world of crypto, not just as a currency but as a tool for ensuring security and preserving anonymity. With expertise in Java, Svelte, EVM, Zero-Knowledge EVM, Solidity, and Web3, I've been at the forefront of projects that bridge real-life with the digital, especially focusing on inter-chain interoperability. My work with Yiddishland, developing efficient web infrastructures, and my training as a Full-Stack Developer, has equipped me to understand and address the challenges of digital ownership in an AI-driven world. Believing in the potential of blockchain beyond finance, I'm passionate about shaping a future where technology stabilizes our world, ensuring fairness and equity for all.
    </div>
    <div></div>
    <div></div>
</div>

