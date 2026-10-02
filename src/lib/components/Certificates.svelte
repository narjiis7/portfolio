<script>
  import graduation from '../../assets/its-graduation.jpeg';
  import hackathon from '../../assets/its-hackathon.jpeg';


  /**
   * @typedef {Object} Certificate
   * @property {string} title
   * @property {string} organization
   * @property {string} year
   * @property {string} image
   */

  /** @type {Certificate[]} */
  const certificates = [
    {
      title: "Iraq Tech School Graduation",
      organization: "Iraq Tech School (ITS) · HUB200",
      year: "2026",
      image:  graduation
    },
    {
      title: "ITS Vision Hackathon",
      organization: "ITS · HUB200",
      year: "2026",
      image:  hackathon
    
    }
  ];

  /** @type {Certificate | null} */
  let selectedCertificate = null;

  /**
   * @param {Certificate} certificate
   */
  function openCertificate(certificate) {
    selectedCertificate = certificate;
  }

  function closeCertificate() {
    selectedCertificate = null;
  }
</script>


<section id="certificates" class="certificates-section">

  <div class="heading">
    <span>04</span>
    <h2>Certificates</h2>
  </div>

  <p class="intro">
    Certificates and achievements that reflect my learning journey
    and participation in technical activities.
  </p>


  <div class="certificates">

    {#each certificates as certificate}

      <div class="certificate-card">

        <button
          class="image-wrapper"
          type="button"
          aria-label={`Open ${certificate.title}`}
          onclick={() => openCertificate(certificate)}
        >
          <span>Certificate</span>
        </button>

        <div class="certificate-info">

          <h3>{certificate.title}</h3>

          <p>{certificate.organization}</p>

          <span>{certificate.year}</span>

          <button type="button" onclick={() => openCertificate(certificate)}>
  View Certificate
</button>

        </div>

      </div>

    {/each}

  </div>

</section>


{#if selectedCertificate}
  <div class="modal">
    <div class="modal-content">

      <button
        class="close"
        type="button"
        onclick={closeCertificate}
      >
        &times;

      </button>

      <img
        src={selectedCertificate.image}
        alt={selectedCertificate.title}
      />

    </div>
  </div>
{/if}

<style>

  .certificates-section {
    padding: 110px 8%;
    background: #ffffff;
  }


  .heading {
    display: flex;
    align-items: center;
    gap: 18px;
    margin-bottom: 15px;
  }


  .heading span {
    color: #8f3b46;
    font-size: 14px;
    font-weight: 700;
    letter-spacing: 2px;
  }


  .heading h2 {
    margin: 0;
    color: #242424;
    font-size: 42px;
  }


  .intro {
    max-width: 600px;
    color: #777;
    line-height: 1.7;
    margin-bottom: 45px;
  }


  .certificates {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
    max-width: 1050px;
  }


  .certificate-card {
    background: #faf8f8;
    border: 1px solid #eee;
    border-radius: 10px;
    overflow: hidden;

    transition: 0.4s ease;

    animation: fadeUp 0.8s ease both;
  }


  .certificate-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.08);
  }


  .image-wrapper {
    width: 100%;
    height: 280px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 0;
    padding: 0;
    overflow: hidden;
    background: #b4232f;
    color: #ffffff;
    cursor: pointer;
    font: inherit;
  }


  .image-wrapper span {
    font-size: 30px;
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
    transition: transform 0.3s ease;
  }


  .image-wrapper:hover span,
  .image-wrapper:focus-visible span {
    transform: scale(1.06);
  }


  .certificate-info {
    padding: 25px;
  }


  .certificate-info h3 {
    margin: 0 0 10px;
    color: #242424;
    font-size: 20px;
  }


  .certificate-info p {
    margin: 0 0 8px;
    color: #777;
    font-size: 14px;
  }


  .certificate-info span {
    display: block;
    margin-bottom: 18px;

    color: #8f3b46;
    font-size: 13px;
    font-weight: 600;
  }


  .certificate-info button {
    padding: 10px 17px;

    border: 1px solid #8f3b46;
    border-radius: 5px;

    background: transparent;
    color: #8f3b46;

    cursor: pointer;

    transition: 0.3s ease;
  }


  .certificate-info button:hover {
    background: #8f3b46;
    color: white;
  }


  /* Modal */

  .modal {
    position: fixed;
    inset: 0;

    display: flex;
    align-items: center;
    justify-content: center;

    padding: 30px;

    background: rgba(20, 20, 20, 0.85);

    z-index: 2000;

    animation: fadeIn 0.3s ease;
  }


  .modal-content {
    position: relative;

    max-width: 1000px;
    max-height: 90vh;
  }


  .modal-content img {
    display: block;

    max-width: 100%;
    max-height: 85vh;

    border-radius: 6px;
  }


  .close {
    position: absolute;

    top: -45px;
    right: 0;

    border: none;
    background: none;

    color: white;
    font-size: 35px;

    cursor: pointer;
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


  @keyframes fadeIn {

    from {
      opacity: 0;
    }

    to {
      opacity: 1;
    }

  }


  @media (max-width: 700px) {

    .certificates-section {
      padding: 80px 6%;
    }

    .heading h2 {
      font-size: 32px;
    }

    .certificates {
      grid-template-columns: 1fr;
    }

    .image-wrapper {
      height: 230px;
    }

  }

</style>e>