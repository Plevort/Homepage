<script context="module">
    export function load({ error }) {
        return {
            status: error?.status || 500,
        };
    }
</script>

<style>
    /* Basic styles for the dark-themed 404 page */
    :global(body) {
        margin: 0;
        padding: 0;
        background-color: #121212; /* Dark background */
        color: #ffffff; /* White text */
        font-family: Arial, sans-serif;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100vh;
        text-align: center;
    }

    h1 {
        font-size: 6rem; /* Size of the 404 text */
        margin: 0;
    }

    .sad-face {
        font-size: 5rem; /* Size of the sad face */
        transform: rotate(90deg); /* Rotate the sad face */
        margin-bottom: 1rem;
    }

    p {
        font-size: 1.5rem; /* Size of the description text */
        margin: 0;
    }

    a {
        color: #bb86fc; /* Link color */
        text-decoration: none;
        font-size: 1.2rem;
        margin-top: 2rem; /* Space between text and button */
        border: 1px solid #bb86fc; /* Border for the button */
        padding: 10px 20px; /* Padding for the button */
        border-radius: 5px; /* Rounded corners */
        transition: background-color 0.3s;
    }

    a:hover {
        background-color: #bb86fc; /* Background color on hover */
        color: #121212; /* Text color on hover */
    }

    /* Adding more space above the button */
    .button-container {
        margin-top: 3rem; /* Adjust this value to move the button lower */
    }
</style>

<div>
    <div class="sad-face">:(</div>
    <h1>404</h1>
    <p>Page Not Found</p>
    <div class="button-container">
        <a href="/">Go Back to Homepage</a>
    </div>
</div>
