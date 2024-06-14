<script lang="ts">
  export let title: String = ""
  export let id: string = ""
</script>

<section {id}>
  <h2>{title}</h2>
  <slot />
</section>

<style>
  h2 {
    font-size: 3.5em;
    font-weight: 600;
    z-index: -1;
    position: relative;
    color: #eff5f5;
  }

  h2::before {
    content: "";
    display: block;
    width: 12rem;
    position: relative;
    top: 4.5rem;
    left: 2rem;
    z-index: -1;
    border-bottom: 30px solid #f6b17a;
  }

  section {
    padding: 24px 80px;
    background: transparent;
    height: 100vh;
    z-index: 9999;
    position: relative;
  }

  @media only screen and (max-width: 768px) {
    section {
      padding: 24px 80px;
      background: transparent;
      height: 100%;
      z-index: 9999;
      position: relative;
    }
  }
</style>
