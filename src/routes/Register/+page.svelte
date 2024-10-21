<script>
    import { writable } from 'svelte/store';

    const email = writable('');
    const password = writable('');
    const username = writable('');
    const error = writable('');
    const success = writable('');

    const registerUser = async () => {
        error.set('');
        success.set('');

        const userData = {
            email: $email,
            password: $password,
            username: $username
        };

        try {
            const response = await fetch('https://plevortapi.fryde.id.lv/v1/register', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(userData)
            });

            if (response.ok) {
                const data = await response.json();
                success.set(data.message);
            } else {
                const data = await response.json();
                if (data.error) {
                    error.set(data.error);
                } else {
                    error.set('An unexpected error occurred. Please try again later.');
                }
            }
        } catch (err) {
            error.set('Network error. Please try again later.');
        }
    };
</script>

<style>
    html, body {
        margin: 0;
        padding: 0;
        overflow: hidden;
        height: 100%;
        background-color: #121212;
        color: #f0f0f0;
        font-family: 'Inter', sans-serif;
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

    nav ul li a:hover {
        background-color: rgba(255, 255, 255, 0.1);
    }

    form {
        display: flex;
        flex-direction: column;
        gap: 1em;
        margin: 2rem 3rem;
    }

    input {
        padding: 0.8rem;
        border-radius: 5px;
        border: 1px solid #444;
        background-color: #222;
        color: #f0f0f0;
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

    label {
        color: #f0f0f0;
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

<form on:submit|preventDefault={registerUser}>
    <input type="email" bind:value={$email} placeholder="Email" required />
    <input type="password" bind:value={$password} placeholder="Password" required />
    <input type="text" bind:value={$username} placeholder="Username" required />
    <label>
        <input type="checkbox" required /> I accept the <a href="./Privacy">Privacy Policy</a> and <a href="./Tos">Terms of Service</a>.
    </label>
    <button type="submit">Register</button>

    {#if $error}
        <p class="error">Error: {$error}</p>
    {/if}
    {#if $success}
        <p class="success">Success: {$success}</p>
    {/if}
</form>
