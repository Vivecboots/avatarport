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
        display: grid;
        grid-template-columns: repeat(6, 1fr);
        gap: 16px;
        width: 88vw;
        margin-top: 6%;
        margin-bottom: 10%;
    }

    .narrative-first, .narrative-second {
        background: url('/mountain.png') no-repeat center center;
        background-size: contain;
        height: auto;
    }

    .narrative-first {
        grid-column: 1/4;
    }

    .narrative-second {
        grid-column: 4/7;
    }

    .skeleton-card-first, .skeleton-card-second {
        padding: 20px;
        border: 0px solid #9400D3; /* Neon purple border */
        border-radius: 8px;
        color: #010101;
        animation: glowing 10s infinite; /* Apply the glowing effect */
        font-family: 'PressStart2P', sans-serif;
        font-size: 1.5rem;
        font-weight: bold;
    }

    .skeleton-card-first {
        grid-column: 4/7;
    }

    .skeleton-card-second {
        grid-column: 1/4;
    }

    @media (max-width: 768px) {
        .grid-container {
            grid-template-columns: 1fr;
            gap: 8px;
        }

        .narrative-first, .skeleton-card-first, .narrative-second, .skeleton-card-second {
            grid-column: 1 / -1;
        }
    }
</style>

<div class="grid-container">
    <!-- First row: picture then card -->
    <div class="narrative-first"></div>
    <div class="skeleton-card-first">
        While crypto is a great conduit of money, at over 1 trillion USD and expected to be multiples of that in the near future, the true value is actually in identity and state change management. Blockchain technology allows permanence in a technological realm where cloning identities takes no more work than clicking a few buttons. As work becomes cheaper and easier, problems of verification will only become more difficult. To ensure ownership in a technological future is challenging, but it is also critical. That is why despite recent downturns, some technologies that are encompassed in the ideology of Web3 are a glimpse into how we will operate in the future. When I was a kid, they said home computers would never progress past toys. Many other predictions came out in my life like that, and many of them were incorrect. I recommend embracing the technology early and piggyback on the great things it offers. Places of extreme interest for me, and what embodies my ideologies, are that of ownership, privacy, and equality. Equality of opportunity, fees, interoperability, and zero-knowledge proofs are among some of the many ways we can achieve this. I see working in this field as an opportunity to make a difference in something that will affect humans for the rest of time as our economy becomes digital. When working in emerging fields, each action taken is amplified. As of now, I’m writing in Typescript, a subset of Javascript, and the reductions keep going until you are left with a person who made a small decision one day to name a function if. And that if changed everything. And that's what led me here, one question about what I stand for as a person, if, if this is what I believe in, then what are the consequences if I don’t do it. I hope to work with only teams that feel the same passion. Finances attract scammers, certainly. But the stock financial sector doesn't let it define it. Rather, they are prestigious. And one day, as the younger generations grow into the role, so will the new technology.
    </div>

    <!-- Second row: card then picture -->
    <div class="skeleton-card-second">
        Blockchain technology, at its core, is about ensuring authenticity in a digital age. As we transition into an era where our identities, assets, and transactions are increasingly digital, the importance of a secure and transparent system becomes paramount. This is where blockchain shines, offering a decentralized and immutable ledger that can verify and record digital transactions without the need for intermediaries. But beyond the technicalities, it's the potential societal impacts of blockchain that truly excite me. The promise of a more transparent, equitable, and decentralized world, where power and control are distributed among its participants, is a vision worth striving for. And as a developer, I have the privilege and responsibility to contribute to this vision, one line of code at a time.
    </div>
    <div class="narrative-second"></div>
</div>
