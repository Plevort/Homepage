<script>
  let username = '';
  let password = '';
  
  const navItems = [
    { name: "Home", href: "/" },
    { name: "Register", href: "./Register" },
    { name: "Login", href: "./Login" },
    { name: "Privacy Policy", href: "/Privacy" },
    { name: "Terms Of Service", href: "/Tos" },
    { name: "Support", href: "/Support" },
  ];

  function handleLogin(event) {
    event.preventDefault();
    console.log('Logging in:', { username, password });
  }
</script>

<header>
  <div class="logo"><a href="/">Plevort</a></div>
  <nav>
    <ul>
      {#each navItems as item}
        <li><a href={item.href}>{item.name}</a></li>
      {/each}
    </ul>
  </nav>
</header>

<section class="form-section">
  <div class="form-container">
    <h1>Login</h1>
    <form on:submit={handleLogin}>
      <div class="form-group">
        <label for="username">Username</label>
        <input type="text" id="username" bind:value={username} required />
      </div>
      <div class="form-group">
        <label for="password">Password</label>
        <input type="password" id="password" bind:value={password} required />
      </div>
      <button type="submit" class="btn">Login</button>
    </form>
  </div>
</section>

<footer>
  <p>© 2024 The Plevort Team</p>
</footer>

<style>
  @import './App.css';
</style>
