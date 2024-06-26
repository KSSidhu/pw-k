<script lang="ts">
  export let name: string
  export let description: string
  export let src: string
  export let link: string
  export let variant: "right" | "left"
</script>

<div class="card" class:left={variant === "left"} class:right={variant === "right"}>
  <div
    class="header"
    class:header-right={variant === "right"}
    class:header-left={variant === "left"}
  >
    <h3 class="header-text">{name}</h3>
  </div>

  <div class="content">
    {#if variant === "right"}
      <div>
        <p class="description">{description}</p>
        <a href={link}>Link</a>
      </div>
    {/if}

    <img {src} alt="" />
    {#if variant === "left"}
      <div>
        <p class="description">{description}</p>
        <a href={link}>Link</a>
      </div>
    {/if}
  </div>
</div>

<style>
  .card {
    background-color: #2d3250;
    padding: 16px;
    border-radius: 16px;
    display: flex;
    flex-direction: column;
    margin: 0;
  }

  .left {
    align-self: flex-start;

    @media only screen and (max-width: 768px) {
      align-self: center;
    }
  }

  .right {
    align-self: flex-end;

    @media only screen and (max-width: 768px) {
      align-self: center;
    }
  }

  .description {
    max-width: 250px;
  }

  .header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  .header-left {
    align-self: flex-end;
    padding-right: 8.5rem;
  }

  .header-right {
    align-self: flex-start;
  }

  .header-text {
    padding: 0;
    margin: 0;
  }

  .content {
    display: flex;
    flex-direction: row;
    gap: 24px;
  }

  p {
    font-size: 1.2rem;
    font-size: 500;

    @media only screen and (max-width: 768px) {
      font-size: 1rem;
    }
  }

  a {
    font-size: 1.2rem;
    font-weight: 700;
    color: #eff5f5;
    text-decoration: none;
    background-color: #f6b17a;
    padding: 8px;
    border-radius: 8px;
  }

  h3 {
    align-self: flex-start;
    padding: 6px 12px;
    font-size: 1.5rem;
    color: #eb6440;
    width: fit-content;
  }

  img {
    height: 500px;
    width: 800px;
    border-radius: 12px;

    @media only screen and (max-width: 768px) {
      height: 200px;
      width: 300px;
    }
  }
</style>
