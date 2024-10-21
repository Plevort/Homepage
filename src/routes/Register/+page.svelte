<script>
  let username = '';
  let password = '';
  let email = '';
  
  function handleRegister(event) {
    event.preventDefault();
    console.log('Registering:', { username, email, password });
  }

  // Define the navigation links array
  let links = [
    { name: "Home", href: "/" },
    { name: "Register", href: "./Register" },
    { name: "Login", href: "./Login" },
    { name: "Privacy Policy", href: "/Privacy" },
    { name: "Terms Of Service", href: "/Tos" },
    { name: "Support", href: "/Support" },
  ];
</script>

<header>
  <div class="logo"><a href="/">Plevort</a></div>
  <nav>
    <ul>
      {#each links as link}
        <li><a href={link.href}>{link.name}</a></li>
      {/each}
    </ul>
  </nav>
</header>

<section class="form-section">
  <div class="form-container">
    <h1>Register</h1>
    <form on:submit={handleRegister}>
      <div class="form-group">
        <label for="username">Username</label>
        <input type="text" id="username" bind:value={username} required />
      </div>
      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" id="email" bind:value={email} required />
      </div>
      <div class="form-group">
        <label for="password">Password</label>
        <input type="password" id="password" bind:value={password} required />
      </div>
      <button type="submit" class="btn">Register</button>
    </form>
  </div>
</section>

<footer>
  <p>© 2024 The Plevort Team</p>
</footer>

<style>
  @import './App.css';
</style>
