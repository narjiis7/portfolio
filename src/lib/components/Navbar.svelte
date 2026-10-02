<script>
  let menuOpen = false;

  function closeMenu() {
    menuOpen = false;
  }
</script>

<nav class="navbar">
  <a href="#home" class="logo" onclick={closeMenu}>NE.</a>

  <!-- Desktop Navigation -->
  <div class="links">
    <a href="#about">About</a>
    <a href="#experience">Experience</a>
    <a href="#skills">Skills</a>
    <a href="#certificates">Certificates</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </div>

  <a href="/CV.pdf" class="cv-button">My CV</a>

  <!-- Mobile Button -->
  <button
    class="menu-button"
    onclick={() => (menuOpen = !menuOpen)}
    aria-label="Toggle menu"
  >
    <span></span>
    <span></span>
    <span></span>
  </button>
</nav>

<!-- Mobile Navigation -->
{#if menuOpen}
  <div class="mobile-menu">
    <a href="#about" onclick={closeMenu}>About</a>
    <a href="#experience" onclick={closeMenu}>Experience</a>
    <a href="#skills" onclick={closeMenu}>Skills</a>
    <a href="#certificates" onclick={closeMenu}>Certificates</a>
    <a href="#projects" onclick={closeMenu}>Projects</a>
    <a href="#contact" onclick={closeMenu}>Contact</a>

    <a href="/CV.pdf" class="mobile-cv" onclick={closeMenu}>
      View My CV
    </a>
  </div>
{/if}


<style>
  .navbar {
    position: fixed;
    top: 0;
    left: 0;

    width: 100%;
    height: 80px;

    padding: 0 8%;

    display: flex;
    align-items: center;
    justify-content: space-between;

    background: rgba(255, 255, 255, 0.9);
    backdrop-filter: blur(12px);

    border-bottom: 1px solid #eee;

    z-index: 1000;
    box-sizing: border-box;

    animation: navbarIn 0.7s ease;
  }


  /* Logo */

  .logo {
    color: #8f3b46;

    font-size: 26px;
    font-weight: 800;

    text-decoration: none;

    transition: 0.3s ease;
  }

  .logo:hover {
    transform: translateY(-2px);
  }


  /* Desktop Links */

  .links {
    display: flex;
    align-items: center;
    gap: 28px;
  }

  .links a {
    position: relative;

    color: #333;

    text-decoration: none;

    font-size: 14px;
    font-weight: 500;

    transition: color 0.3s ease;
  }

  .links a::after {
    content: "";

    position: absolute;

    left: 0;
    bottom: -7px;

    width: 0;
    height: 1.5px;

    background: #8f3b46;

    transition: width 0.3s ease;
  }

  .links a:hover {
    color: #8f3b46;
  }

  .links a:hover::after {
    width: 100%;
  }


  /* CV Button */

  .cv-button {
    padding: 10px 18px;

    border: 1px solid #8f3b46;
    border-radius: 5px;

    color: #8f3b46;

    text-decoration: none;

    font-size: 13px;
    font-weight: 600;

    transition: 0.3s ease;
  }

  .cv-button:hover {
    background: #8f3b46;
    color: white;

    transform: translateY(-2px);
  }


  /* Mobile Button */

  .menu-button {
    display: none;

    border: none;
    background: none;

    cursor: pointer;

    padding: 5px;
  }

  .menu-button span {
    display: block;

    width: 25px;
    height: 2px;

    margin: 5px 0;

    background: #8f3b46;
  }


  /* Mobile Menu */

  .mobile-menu {
    display: none;
  }


  /* Animation */

  @keyframes navbarIn {
    from {
      opacity: 0;
      transform: translateY(-15px);
    }

    to {
      opacity: 1;
      transform: translateY(0);
    }
  }


  /* Responsive */

  @media (max-width: 850px) {

    .links,
    .cv-button {
      display: none;
    }

    .menu-button {
      display: block;
    }

    .mobile-menu {
      position: fixed;

      top: 80px;
      left: 0;

      width: 100%;

      display: flex;
      flex-direction: column;

      padding: 25px 8%;

      background: rgba(255, 255, 255, 0.98);

      border-bottom: 1px solid #eee;

      box-sizing: border-box;

      z-index: 999;

      animation: menuIn 0.3s ease;
    }

    .mobile-menu a {
      padding: 14px 0;

      color: #333;

      text-decoration: none;

      border-bottom: 1px solid #f1eeee;

      font-size: 15px;
    }

    .mobile-menu a:hover {
      color: #8f3b46;
    }

    .mobile-menu .mobile-cv {
      margin-top: 15px;

      padding: 12px;

      text-align: center;

      border: 1px solid #8f3b46;
      border-radius: 5px;

      color: #8f3b46;
    }

    @keyframes menuIn {
      from {
        opacity: 0;
        transform: translateY(-10px);
      }

      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
  }
</style>