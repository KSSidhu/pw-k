<script lang="ts">
  export let name: string
  export let src: string
  export let link: string
</script>

<div class="card">
  <div class="header">
    <h3>{name}</h3>
    <a href={link}>Link</a>
  </div>

  <img {src} alt="" />

  <div>
    <p>Hello</p>
  </div>
</div>

<style>
  .card {
    background-color: #2d3250;
    padding: 16px;
    border-radius: 16px;
    display: flex;
    flex-direction: column;
  }

  .header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  p {
    font-size: 1.2rem;
    font-size: 500;
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
    border-radius: 12px;
  }
</style>
