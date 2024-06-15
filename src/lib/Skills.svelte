<div class="skills">
  <div class="skill-list small-logo">
    <div class="skill-square">
      <img src="logos/css.png" alt="" />
      <div class="text">CSS</div>
    </div>

    <div class="skill-square">
      <img src="logos/git.png" alt="" />
      <div class="text">Git</div>
    </div>
    <div class="skill-square">
      <img src="logos/vim.png" alt="" />
      <div class="text">Vim</div>
    </div>
  </div>

  <div class="skill-list large-logo">
    <div class="skill-square">
      <img src="logos/react.png" alt="" />
      <div class="text">React</div>
    </div>
    <div class="skill-square">
      <img src="logos/svelte.png" alt="" />
      <div class="text">Svelte</div>
    </div>
    <div class="skill-square">
      <img src="logos/typescript.png" alt="" />
      <div class="text">Typescript</div>
    </div>
    <div class="skill-square">
      <img src="logos/js.png" alt="" />
      <div class="text">Javascript</div>
    </div>
  </div>

  <div class="skill-list large-logo">
    <div class="skill-square">
      <img src="logos/database.png" alt="" />
      <div class="text">Postgres</div>
    </div>
    <div class="skill-square">
      <img src="logos/graphql.png" alt="" />
      <div class="text">GraphQL</div>
    </div>
    <div class="skill-square">
      <img src="logos/golang.png" alt="" />
      <div class="text">Go</div>
    </div>
  </div>
</div>

<style>
  img {
    height: 60px;
    width: auto;
    border-radius: 8px;
  }

  .text {
    text-align: center;
    font-size: 1.4rem;
    font-weight: 600;
    margin: 0;
    padding: 0;
  }

  .skills {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 45px;
  }

  .skill-list {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .skill-square {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    border: 5px solid #fac277;
    border-radius: 12px;
  }

  .small-logo > div {
    padding: 0.5em 2em;
  }

  .large-logo > div {
    padding: 0.5em 1em;
  }

  @media only screen and (max-width: 768px) {
    img {
      height: 50px;
    }

    .skill-square {
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      border: 5px solid #fac277;
      border-radius: 12px;
    }

    .small-logo > div {
      padding: 0.75em 2.25em;
    }

    .large-logo > div {
      padding: 0.75em 1.75em;
    }

    .text {
      text-align: center;
      font-size: 1rem;
      font-weight: 600;
    }
  }
</style>
