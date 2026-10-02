<script>
  const skillGroups = [
    {
      title: "Languages",
      skills: ["HTML", "CSS", "JavaScript",  "Dart"]
    },
    {
      title: "Frameworks & Libraries",
      skills: ["Svelte", "React" , "Flutter"]
    },
    {
      title: "Tools & Technologies",
      skills: [ "Visual Studio",  "Cursor",  "GitHub" , "Git"]
    },
   
  ];
</script>

<section id="skills" class="section">
  <div class="section-heading">
    <span>03</span>
    <h2>Skills</h2>
  </div>

  <div class="skills-container">
    {#each skillGroups as group}
      <div class="skill-group">
        <h3>{group.title}</h3>

        <div class="skills-list">
          {#each group.skills as skill}
            <div class="skill">
              {skill}
            </div>
          {/each}
        </div>
      </div>
    {/each}
  </div>
</section>

<style>
  .section {
    padding: 110px 8%;
    background: #ffffff;
  }

  .section-heading {
    display: flex;
    align-items: center;
    gap: 15px;
    margin-bottom: 60px;
  }

  .section-heading span {
    color: #8f3b46;
    font-size: 14px;
    font-weight: 600;
  }

  .section-heading h2 {
    margin: 0;
    font-size: 40px;
    color: #242424;
  }

  .skills-container {
    max-width: 900px;
  }

  .skill-group {
    padding: 25px 0;
    border-bottom: 1px solid #eee;
  }

  .skill-group:first-child {
    border-top: 1px solid #eee;
  }

  .skill-group h3 {
    margin: 0 0 18px;
    color: #555;
    font-size: 16px;
    font-weight: 600;
  }

  .skills-list {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
  }

  .skill {
    padding: 11px 20px;
    border: 1px solid #eadcdf;
    border-radius: 6px;
    background: #faf8f8;
    color: #333;
    font-size: 14px;
    transition: all 0.3s ease;
  }

  .skill:hover {
    transform: translateY(-4px);
    border-color: #8f3b46;
    color: #8f3b46;
    box-shadow: 0 8px 20px rgba(143, 59, 70, 0.08);
  }

  @media (max-width: 600px) {
    .section {
      padding: 80px 6%;
    }

    .section-heading h2 {
      font-size: 32px;
    }

    .skill {
      padding: 10px 15px;
    }
  }
</style>