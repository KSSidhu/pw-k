<script>
  import Section from "./ui/Section.svelte"
</script>

<Section id="contact" title={"Contact"}>
  <div class="card">
    <div class="greeting">
      Can shoot me a message here, or over on <a
        href="https://www.linkedin.com/in/gurkiratsidhu-1805">LinkedIn</a
      >
    </div>

    <form action="https://getform.io/f/paoxvzpb" method="POST">
      <input placeholder="Name" type="text" name="name" />
      <input placeholder="Email" type="email" name="email" />
      <textarea rows="10" placeholder="Message" name="message" />
      <!-- add hidden Honeypot input to prevent spams -->
      <input type="hidden" name="_gotcha" style="display:none !important" />
      <button type="submit">Send</button>
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
    gap: 24px;
  }

  button {
    align-self: flex-start;
    width: 20%;
    padding: 12px;
    font-size: 1rem;
  }

  input {
    padding: 8px;
    border-radius: 8px;
    background-color: "#7077A1";
    font-size: 1rem;
    outline: none;
  }

  textarea {
    padding: 8px;
    resize: none;
    font-size: 1rem;
    outline: none;
  }

  .card {
    display: flex;
    flex-direction: column;
    gap: 48px;
    background-color: #2d3250;
    padding: 20px;
    border-radius: 12px;
    width: 60%;

    @media only screen and (max-width: 768px) {
      width: 100%;
    }
  }
</style>
