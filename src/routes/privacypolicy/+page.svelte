<script>
  let links = [
    { name: "Home", href: "/" },
    { name: "Register", href: "./register" },
    { name: "Login", href: "./login" },
    { name: "Privacy Policy", href: "/privacypolicy" },
    { name: "Terms Of Service", href: "/tos" },
    { name: "Support", href: "/support" },
  ];
  import "./privacy.css";
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

<main class="content">
  <div class="policy-container">
    <h1>Privacy Policy</h1>
    <p><strong>Effective Date:</strong> 21.10.2024</p>
    <p>Plevort (“we,” “our,” or “us”) is committed to protecting your privacy. This Privacy Policy outlines how we collect, use, disclose, and safeguard your information when you use our chat application. Please read this policy carefully. By using our services, you agree to the collection and use of information in accordance with this policy.</p>
    
    <h2>1. Information We Collect</h2>
    <p>We collect the following information from you when you register and use our chat app:</p>
    <ul>
      <li><strong>Personal Information:</strong> This includes your email address, password, and username.</li>
      <li><strong>Messages:</strong> Any messages you send in private or public chat rooms.</li>
      <li><strong>Usage Data:</strong> We may collect information about how you use our app, including the duration of your chats, timestamps, and interaction patterns.</li>
    </ul>

    <h2>2. Use of Your Information</h2>
    <p>We use the information we collect for the following purposes:</p>
    <ul>
      <li>To provide and maintain our chat services.</li>
      <li>To manage your account and provide customer support.</li>
      <li>To improve our app's functionality and user experience.</li>
      <li>To communicate with you, including sending you updates and promotions (if you have opted in).</li>
    </ul>

    <h2>3. Data Encryption</h2>
    <p><strong>Encryption:</strong> We keep your personal information (email, password, username, messages) encrypted to protect your data from unauthorized access.</p>
    <p><strong>Public Chat Rooms:</strong> Please note that messages sent in public chat rooms are not encrypted and are visible to other users.</p>

    <h2>4. Data Breaches</h2>
    <p>While we take appropriate measures to protect your information, we cannot guarantee absolute security. If a data breach occurs, we will notify affected users as required by law. However, we cannot be held responsible for any unauthorized access or loss of your information or messages.</p>

    <h2>5. Third-Party Disclosure</h2>
    <p>We do not sell, trade, or otherwise transfer your personal information to third parties without your consent, except in the following circumstances:</p>
    <ul>
      <li><strong>Service Providers:</strong> We may share your information with trusted third-party service providers who assist us in operating our app, conducting our business, or servicing you, so long as those parties agree to keep this information confidential.</li>
      <li><strong>Legal Compliance:</strong> We may disclose your information when required to do so by law or in response to valid requests by public authorities.</li>
    </ul>

    <h2>6. User Rights</h2>
    <p>You have the following rights regarding your personal information:</p>
    <ul>
      <li><strong>Access:</strong> You can request access to the personal information we hold about you.</li>
      <li><strong>Correction:</strong> You can request that we correct any inaccurate or incomplete personal information.</li>
      <li><strong>Deletion:</strong> You can request the deletion of your personal information, subject to certain exceptions.</li>
    </ul>

    <h2>7. Changes to This Privacy Policy</h2>
    <p>We may update this Privacy Policy from time to time. We will notify you of any changes by posting the new policy on this page. You are advised to review this Privacy Policy periodically for any changes. Changes to this policy are effective when they are posted on this page.</p>

    <h2>8. Contact Us</h2>
    <p>If you have any questions about this Privacy Policy, or want your data to be deleted please contact us at:</p>
    <p><strong>Email:</strong>plevortapp@gmail.com</p>
  </div>
</main>

<footer>
  <p>© 2024 The Plevort Team</p>
</footer>