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
  
  <div class="support-container">
    <div class="support-text">
      <h1>plevortapp@gmail.com</h1>
      <h1>Support Page</h1>
      <p>If you have any questions or need assistance, please don't hesitate to reach out to us.</p>
      <p>To contact our support team, simply send us an email.</p>
      <p>We aim to respond to all inquiries within 24 hours. Thank you for reaching out!</p>
      <p>We appreciate your patience as we work to resolve your concerns.</p>
      <p>Remember, your feedback is important to us and helps improve our services.</p>
    </div>
    <div class="example-email">
      <h2>Example Email</h2>
      <p>Subject: Account Deletion</p>
      <p>Message: I need help with my account. I would like to delete it since I don’t use this application anymore. Could you please clear my information?</p>
      <p>Thanks,</p>
      <p class="username">Username: example_user</p>
      <p class="real-name">Real Name: John Doe</p>
    </div>
  </div>
  
  <footer>
    <p>© 2024 The Plevort Team</p>
  </footer>
  
  <style>
    body {
      background-color: #000000;
      color: #ffffff;
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      height: 100vh;
    }
  
    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background-color: #000000;
      padding: 1rem 3rem;
    }
  
    .logo {
      font-size: 2rem;
      font-weight: bold;
      color: #ffffff;
    }
  
    nav {
      margin-left: auto;
    }
  
    nav ul {
      display: flex;
      list-style: none;
    }
  
    nav ul li {
      margin-left: 3rem;
    }
  
    nav ul li a {
      color: #ffffff;
      text-decoration: none;
      font-size: 1.1rem;
      padding: 0.5rem 1rem;
      border-radius: 5px;
    }
  
    .support-container {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 20px;
      flex-grow: 1;
      margin-top: 50px;
    }
  
    .support-text {
      max-width: 60%;
      text-align: left;
    }
  
    .example-email {
      border: 1px solid #ffffff;
      border-radius: 5px;
      padding: 20px;
      background-color: #1c1c1c; 
      width: 30%;
    }
  
    .example-email h2 {
      margin: 0;
      color: #ffffff;
    }
  
    .example-email p {
      margin: 5px 0 0 0;
      color: #ffffff;
    }
  
    .example-email .username {
      margin-top: 10px;
      font-weight: bold;
    }
  
    .example-email .real-name {
      margin-top: 5px;
      font-style: italic;
    }
  
    footer {
      background-color: #000000;
      width: 100%;
      padding: 1rem;
      text-align: center;
      font-size: 1.2rem;
      position: relative;
      bottom: 0;
      color: #ffffff;
    }
  </style>
  