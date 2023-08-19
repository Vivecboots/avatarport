<script>
    import { onMount } from 'svelte';

    let name = "";
    let email = "";
    let message = "";
    let formSent = false;

    onMount(() => {
        // Dynamically load the EmailJS SDK
        const script = document.createElement('script');
        script.src = 'https://cdn.emailjs.com/dist/email.min.js';
        script.onload = () => {
            // Initialize EmailJS with your user_id
            window.emailjs.init('blair');
        };
        document.body.appendChild(script);
    });

    function handleSubmit() {
    // Send the email using EmailJS
    window.emailjs.send('service_whwonuc', 'template_bymloll', {
        from_name: name,
        from_email: email,
        message: message,
        to_email: 'Blairwin05@gmail.com'
    }, 'yYw_FP2TjeZvS4KtK').then(() => {
        formSent = true;
        name = "";
        email = "";
        message = "";
    }).catch(error => {
        console.error('Email sending failed:', error);
    });
}

</script>

<svelte:head>
    <style>
        .contact-card {
            background-color: #303c7e;
            box-shadow: 0 2px 8px rgba(57, 255, 20, 0.6);
            overflow: hidden;
            max-width: 500px;
            margin: 2rem auto;
            margin-top: -15%;
            color: #000;
        }

        .contact-header {
            background-color: #9723e8;
            color: #000;
            padding: 1rem;
            font-size: 1.25rem;
            text-align: center;
            font-weight: bold;
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            padding: 2rem;
        }

        input.contact-input, textarea.contact-input {
            padding: 0.5rem;
            border: none;
            font-size: 1rem;
            background-color: #4a5a9e; /* Lighter shade of blue */
            color: #FF69B4; /* Neon pink */
            font-weight: bold; /* Bold text */
        }

        .contact-submit {
            background-color: #000;
            color: #000;
            padding: 0.75rem 1rem;
            border: none;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .contact-submit:hover {
            background-color: #39ff90;
        }

        .thank-you-message {
            font-size: 1.3rem; /* Adjusted font size */
            padding: 1% 5%; /* Percentage-based padding */
            text-align: center; /* Center the text */
        }
    </style>
</svelte:head>

<div class="contact-card">
    {#if formSent}
        <div class="thank-you-message">Thank you for your message! We'll get back to you shortly.</div>
    {:else}
        <div class="contact-header">Drop a Line</div>
        <form class="contact-form" on:submit|preventDefault={handleSubmit}>
            <input
                class="contact-input"
                type="text"
                placeholder="Your Name"
                bind:value={name}
                required
            />
            <input
                class="contact-input"
                type="email"
                placeholder="Your Email"
                bind:value={email}
                required
            />
            <textarea
                class="contact-input"
                rows="4"
                placeholder="Your Message"
                bind:value={message}
                required
            ></textarea>
            <button class="contact-submit" type="submit">Send Message</button>
        </form>
    {/if}
</div>
