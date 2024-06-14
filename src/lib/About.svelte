<script>
  import Skills from "./Skills.svelte"
  import Section from "./ui/Section.svelte"
</script>

<hr class="divider" />
<Section id="about" title="About">
  <div class="profile-cols">
    <div class="card about-me">
      <img src="images/profile.JPG" alt="default" />
      <p>
        I'm a software developer with proven industry experience working as a full-stack
        developer at Sierra wireless on their Airlink Mobility Manager product and as a
        front-end developer at SAP on their Analytics Cloud product. Continuously
        furthering my knowledge in web development. Currently very invested in learning
        more about Golang, React, Docker, and GraphQL
      </p>
    </div>

    <div class="card about-me">
      <Skills />
    </div>
  </div>
</Section>

<style>
  img {
    border-radius: 50%;
    height: 45%;
  }

  p {
    font-size: 1.2em;
    font-weight: 500;
    color: #d6e4e5;
  }

  .divider {
    height: 25px;
    background-color: #eb6440;
    position: relative;
  }

  .card {
    background-color: #7077a1;
    padding: 1.4em;
    border-radius: 12px;
  }

  .about-me {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .profile-cols {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 125px;
  }

  @media only screen and (max-width: 768px) {
    .profile-cols {
      display: flex;
      flex-direction: column;
    }

    .card {
      background-color: #7077a1;
      padding: 1.4rem;
      border-radius: 12px;
    }
  }
</style>
