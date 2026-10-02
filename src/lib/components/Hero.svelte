<section id="home" class="hero">
  <div class="content">
    <p class="small-title">Hello, I'm</p>

    <h1>Narjis Eehab</h1>

    <h2>Junior Software Developer</h2>

    <p class="description">
      Junior software developer with a foundation in web development and hands-on experience building front-end projects. 
      Currently focused on Flutter and mobile application development.
    </p>

    <div class="buttons">
      <a href="#projects" class="primary">View Projects</a>
      <a href="#contact" class="secondary">Contact Me</a>
    </div>
  </div>

  <div class="shape"></div>
</section>

<style>
  .hero {
    min-height: 100vh;
    padding: 120px 8% 60px;
    box-sizing: border-box;
    display: flex;
    align-items: center;
    position: relative;
    overflow: hidden;
    background: #faf8f8;
  }

  .content {
    max-width: 700px;
    animation: fadeUp 1s ease;
    z-index: 2;
  }

  .small-title {
    color: #8f3b46;
    font-weight: 600;
    letter-spacing: 2px;
  }

  h1 {
    font-size: clamp(55px, 8vw, 95px);
    margin: 10px 0;
    color: #242424;
    line-height: 1;
  }

  h2 {
    color: #8f3b46;
    font-size: 25px;
    font-weight: 500;
  }

  .description {
    max-width: 600px;
    color: #666;
    line-height: 1.8;
    font-size: 17px;
  }

  .buttons {
    display: flex;
    gap: 15px;
    margin-top: 35px;
  }

  .buttons a {
    padding: 13px 25px;
    border-radius: 6px;
    text-decoration: none;
    transition: 0.3s;
  }

  .primary {
    background: #8f3b46;
    color: white;
  }

  .primary:hover {
    transform: translateY(-3px);
  }

  .secondary {
    border: 1px solid #8f3b46;
    color: #8f3b46;
  }

  .secondary:hover {
    background: #f4e8ea;
  }

  .shape {
    position: absolute;
    right: -180px;
    width: 500px;
    height: 500px;
    border-radius: 50%;
    background: #f4e8ea;
    animation: floating 5s ease-in-out infinite;
  }

  @keyframes fadeUp {
    from {
      opacity: 0;
      transform: translateY(30px);
    }

    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes floating {
    0%, 100% {
      transform: translateY(0);
    }

    50% {
      transform: translateY(-20px);
    }
  }
</style>