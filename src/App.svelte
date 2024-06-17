<script lang="ts">
  import About from "./lib/About.svelte"
  import Contact from "./lib/Contact.svelte"
  import Hero from "./lib/Hero.svelte"
  import Projects from "./lib/Projects.svelte"
  import Navbar from "./lib/ui/Navbar.svelte"
  import Section from "./lib/ui/Section.svelte"
  import SectionBackground from "./lib/ui/SectionBackground.svelte"
</script>

<main>
  <Hero />
  <Navbar />

  <SectionBackground />

  <About />

  <Projects />

  <Contact />
</main>
