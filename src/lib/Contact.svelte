<script>
  import Section from "./ui/Section.svelte"
</script>

<Section id="contact" title={"Contact"}>
  <div class="card">
    <div>
      Can shoot me a message here, or over on <a
        href="https://www.linkedin.com/in/gurkiratsidhu-1805">LinkedIn</a
      >
    </div>

    <form>
      <input placeholder="ENTER HERE" />
      <input placeholder="ENTER HERE" />
      <input placeholder="ENTER HERE" />
      <input placeholder="ENTER HERE" />
    </form>
  </div>
</Section>

<style>
  div {
    font-size: 1.25rem;
  }

  a {
    color: #eb6440;
  }

  form {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  input {
    padding: 8px;
    border-radius: 8px;
  }

  .card {
    display: flex;
    flex-direction: column;
    gap: 48px;
    background-color: #2d3250;
    padding: 20px;
    border-radius: 12px;
  }
</style>
