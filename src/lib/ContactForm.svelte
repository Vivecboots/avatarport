<script>
    let name = ""; // Declaring the variable 'name'
    let email = ""; // Declaring the variable 'email'
    let message = ""; // Declaring the variable 'message'
    let formSent = false;

    function handleSubmit() {
        // Here you can add logic to send the form data to your backend or any API endpoint.
        // For the sake of this demonstration, we'll simply reset the form and show a success message.
        formSent = true;
        name = "";
        email = "";
        message = "";
    }
</script>



<svelte:head>
    <style>
        .contact-card {
            background-color: #303c7e; 
            box-shadow: 0 2px 8px rgba(57, 255, 20, 0.6); /* Neon green shadow */
            overflow: hidden;
            max-width: 500px;
            margin: 2rem auto;
            margin-top: -15%;
            color: #000; /* Make text black */
        }
        
        .contact-header {
            background-color: #9723e8;
            color: #000; /* Make header text black */
            padding: 1rem;
            font-size: 1.25rem;
            text-align: center;
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            padding: 2rem;
        }

        .contact-input {
            padding: 0.5rem;
            border: none; 
            font-size: 1rem;
            background-color: rgba(255, 255, 255, 0.7);
            color: #000; /* Make input text black */
        }

        .contact-submit {
            background-color: #39ff14;
            color: #000; /* Make button text black */
            padding: 0.75rem 1rem;
            border: none;
            cursor: pointer;
            transition: background-color 0.3s; /* Smooth transition */
        }

        .contact-submit:hover {
            background-color: #ff4500; /* Neon orange color on hover */
        }
    </style>
</svelte:head>

<div class="contact-card">
    {#if formSent}
        <p>Thank you for your message! We'll get back to you shortly.</p>
    {:else}
        <div class="contact-header">Contact Us</div>
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

