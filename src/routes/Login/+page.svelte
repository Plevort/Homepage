<!-- src/Login.svelte -->
<script>
    import { writable } from 'svelte/store';

    const email = writable('');
    const password = writable('');
    const error = writable('');
    const success = writable('');

    const loginUser = async () => {
        error.set('');
        success.set('');

        const response = await fetch('https://plevortapi.fryde.id.lv/v1/login', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                email: $email,
                password: $password
            })
        });

        if (response.ok) {
            const data = await response.json();
            success.set(data.message); // Customize this based on your API response
        } else {
            const data = await response.json();
            if (data.error) {
                error.set(data.error);
            } else {
                error.set('An unexpected error occurred. Please try again later.');
            }
        }
    };
</script>

<style>
    /* Styles for the login form */
    form {
        display: flex;
        flex-direction: column;
        gap: 1em;
        margin: 1rem 0;
    }

    input {
        padding: 0.8rem;
        border-radius: 5px;
        border: 1px solid #ccc;
    }

    button {
        background-color: #5865F2;
        color: #fff;
        padding: 1rem;
        border-radius: 5px;
        border: none;
        cursor: pointer;
    }

    .error {
        color: red;
    }

    .success {
        color: green;
    }

    header {
        display: flex;
        justify-content: space-between;
        padding: 1.5rem 3rem;
        background-color: #111;
    }

    .logo {
        font-size: 2rem;
        font-weight: bold;
    }

    nav ul {
        display: flex;
        list-style: none;
    }

    nav ul li {
        margin-left: 3rem;
    }

    nav ul li a {
        color: #f0f0f0;
        text-decoration: none;
        font-size: 1.1rem;
        padding: 0.5rem 1rem;
        border-radius: 5px;
    }
</style>

<header>
    <div class="logo">Plevort</div>
    <nav>
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="./Register">Register</a></li>
            <li><a href="./Login">Login</a></li>
            <li><a href="./Privacy">Privacy Policy</a></li>
            <li><a href="./Tos">Terms of Service</a></li>
            <li><a href="/Support">Support</a></li>
        </ul>
    </nav>
</header>

<form on:submit|preventDefault={loginUser}>
    <input type="email" bind:value={$email} placeholder="Email" required />
    <input type="password" bind:value={$password} placeholder="Password" required />
    <button type="submit">Login</button>

    {#if $error}
        <p class="error">Error: {$error}</p>
    {/if}
    {#if $success}
        <p class="success">Success: {$success}</p>
    {/if}
</form>
