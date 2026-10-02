<script>
  let projects = [
    {
      number: "01",
      title: "Qanoni — Smart Arabic Legal Platform",
      description:
        "Educational team project for a legal services platform. I contributed to the front-end development, including the interface for legal requests, lawyer services, and contract workflows. The back-end is currently unavailable, so some features may not work in this preview.",
      tech: "Svelte · JavaScript · CSS · Vite",
      link: "https://arabic-legal7-document.vercel.app/"
    },
    {
      number: "02",
      title: "Student Tables",
      description:
        "Educational front-end project for displaying and managing student information through a table-based interface.",
      tech: "React · JavaScript · CSS",
      link: "https://students-tabels-my-app.vercel.app/"
    }
  ];
</script>

<section id="projects" class="section">
  <div class="title">
    <span>04</span>
    <h2>Projects</h2>
  </div>

  <div class="projects">
    {#each projects as project}
      <article class="card">
        <span class="number">{project.number}</span>

        <h3>
          <a
            href={project.link}
            target="_blank"
            rel="noopener noreferrer"
            aria-label={`Open ${project.title} project`}
          >
            {project.title}
          </a>
        </h3>

        <p>{project.description}</p>

        <div class="tech">{project.tech}</div>

        <a
          class="project-link"
          href={project.link}
          target="_blank"
          rel="noopener noreferrer"
        >
          View Project →
        </a>
      </article>
    {/each}
  </div>
</section>

<style>
  .section {
    padding: 110px 8%;
    background: #faf8f8;
  }

  .title {
    display: flex;
    gap: 15px;
    align-items: center;
    margin-bottom: 50px;
  }

  .title span {
    color: #8f3b46;
  }

  h2 {
    margin: 0;
    font-size: 38px;
  }

  .projects {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 25px;
  }

  .card {
    min-height: 300px;
    padding: 35px;
    display: flex;
    flex-direction: column;
    background: white;
    border: 1px solid #eee;
    border-radius: 10px;
    transition: 0.4s;
  }

  .card:hover {
    transform: translateY(-8px);
    border-color: #d9b9be;
    box-shadow: 0 15px 35px rgba(50, 20, 20, 0.08);
  }

  .number {
    color: #8f3b46;
    font-size: 14px;
  }

  h3 {
    margin: 25px 0 10px;
    font-size: 25px;
  }

  h3 a {
    color: #242424;
    text-decoration: none;
  }

  h3 a:hover,
  .project-link:hover {
    color: #8f3b46;
  }

  p {
    color: #666;
    line-height: 1.7;
  }

  .tech {
    margin-top: auto;
    margin-bottom: 20px;
    color: #8f3b46;
    font-size: 13px;
  }

  .project-link {
    color: #242424;
    text-decoration: none;
    font-weight: 600;
  }

  @media (max-width: 900px) {
    .projects {
      grid-template-columns: 1fr;
    }
  }
</style>