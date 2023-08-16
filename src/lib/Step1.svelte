<style>
    .gif-container {
        position: relative; /* Set the container to relative positioning */
        height: 55.66vh;
    }

    .overlay-list {
        position: absolute; /* Overlay will be positioned absolutely within the gif-container */
        top: 10%; /* Adjust these values to position the overlay as needed */
        left: 10%;
        color: white; /* Set the text color to white for visibility on the gif */
        z-index: 1; /* Ensure the overlay appears above the gif */
        margin-left: 40%;
    }

    .overlay-list ul {
        list-style-type: none; /* Remove bullet points */
        padding: 0;
        margin: 0;
    }

    .overlay-list li img {
        width: 50px; /* Adjust the avatar size as needed */
        vertical-align: middle; /* Align the image with the text */
        margin-right: 10px; /* Space between the avatar and text */
    }
</style>

<div class="gif-container">
    <img src="/midinghtgame.gif" alt="Train GIF" />
    <div class="overlay-list">
        <ul>
            <li>
                <img src="mehead.png" alt="Random Avatar">
                Where you at?  You said 4:00 and its almost dinner now..
            </li>
        </ul>
    </div>
</div>
