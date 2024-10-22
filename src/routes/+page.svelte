<script>
  let links = [
    { name: "Home", href: "/" },
    { name: "Register", href: "/register" },
    { name: "Login", href: "/login" },
    { name: "Privacy Policy and TOS", href: "/privacyandterms" },
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
      <a href="https://app.plevort.fryde.id.lv/" class="btn">Get started!</a>
    </div>
  </div>
</section>

<footer>
  <p>© 2024 The Plevort Team</p>
</footer>

<style>
  @import './App.css';
</style>
