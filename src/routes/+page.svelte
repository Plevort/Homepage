<script>
  let links = [
    { name: "Home", href: "/" },
    { name: "Register", href: "./register" },
    { name: "Login", href: "./login" },
    { name: "Privacy Policy", href: "/privacypolicy" },
    { name: "Terms Of Service", href: "/tos" },
    { name: "Support", href: "/support" },
  ];
</script>

<header>
  <div class="logo">Plevort</div>
  <nav>
    <ul>
      {#each links as link}
        <li><a href={link.href}>{link.name}</a></li>
      {/each}
    </ul>
  </nav>
</header>

<section class="hero">
  <div class="hero-content">
    <h1>Welcome to Plevort</h1>
    <p>Connect with your friends and communities with our amazing chat app.</p>
    <div class="buttons">
      <a href="./register" class="btn">Register</a>
      <a href="./login" class="btn">Login</a>
    </div>
  </div>
</section>

<footer>
  <p>© 2024 The Plevort Team</p>
</footer>

<style>
  @import './App.css';
</style>
