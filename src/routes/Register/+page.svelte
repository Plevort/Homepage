<script>
    import { writable } from 'svelte/store';
  
    const email = writable('');
    const password = writable('');
    const passwordConfirm = writable('');
    const username = writable('');
    const error = writable('');
    const success = writable('');
  
    const registerUser = async () => {
        error.set('');
        success.set('');
  
        const userData = {
            email: $email,
            password: $password,
            passwordConfirm: $passwordConfirm,
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
                error.set(data.error || 'An unexpected error occurred.');
            }
        } catch (err) {
            console.error(err);
            error.set('Network error. Please try again later.');
        }
    };

    import './register.css';
</script>
  
<header>
    <div class="logo">Plevort</div>
    <nav>
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/register">Register</a></li>
            <li><a href="/login">Login</a></li>
            <li><a href="/privacy">Privacy Policy</a></li>
            <li><a href="/tos">Terms of Service</a></li>
            <li><a href="/support">Support</a></li>
        </ul>
    </nav>
</header>

<form on:submit|preventDefault={registerUser}>
    <label for="email">Email</label>
    <input type="email" id="email" bind:value={$email} placeholder="e.g., example@domain.com" required />

    <label for="password">Password</label>
    <input type="password" id="password" bind:value={$password} placeholder="e.g., jSZ5?G23AKh7" required />

    <label for="passwordConfirm">Confirm Password</label>
    <input type="password" id="passwordConfirm" bind:value={$passwordConfirm} placeholder="e.g., jSZ5?G23AKh7" required />

    <label for="username">Username</label>
    <input type="text" id="username" bind:value={$username} placeholder="e.g., johndoe123" required />

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
