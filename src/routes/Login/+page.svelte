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
            success.set(data.message);
        } else {
            const data = await response.json();
            if (data.error) {
                error.set(data.error);
            } else {
                error.set('An unexpected error occurred. Please try again later.');
            }
        }
    };

    import "./login.css";
</script>

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
    <label for="email">Email</label>
    <input type="email" id="email" bind:value={$email} placeholder="e.g., example@domain.com" required />

    <label for="password">Password</label>
    <input type="password" id="password" bind:value={$password} placeholder="e.g., jSZ5?G23AKh7" required />

    <button type="submit">Login</button>

    {#if $error}
        <p class="error">Error: {$error}</p>
    {/if}
    {#if $success}
        <p class="success">Success: {$success}</p>
    {/if}
</form>
