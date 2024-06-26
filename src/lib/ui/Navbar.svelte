<script lang="ts">
  import { onMount } from "svelte"

  type Page = "hero" | "about" | "projects" | "contact"
  let page: Page = "hero"

  const options = {
    root: null,
    rootMargin: "0px",
    threshold: 0.5,
  }

  const projectsOptions = {
    root: null,
    rootMargin: "0px",
    threshold: 0.2,
  }

  onMount(() => {
    // Mount observer to update selected nav item as we scroll
    let observer = new IntersectionObserver(navFadeIn, options)

    let projectsObserver = new IntersectionObserver(navFadeIn, projectsOptions)

    observer.observe(document.querySelector("#hero")!)
    observer.observe(document.querySelector("#about")!)
    observer.observe(document.querySelector("#contact")!)

    projectsObserver.observe(document.querySelector("#projects")!)
  })

  function navFadeIn(entries: IntersectionObserverEntry[], _: IntersectionObserver) {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        setPage(entry.target.id as Page)
      }
    })
  }

  function setPage(selectedPage: Page) {
    page = selectedPage
  }
</script>

<nav>
  <ul>
    <li class:selected={page === "hero"}>
      <a href="#hero" on:click={() => setPage("hero")}>Home</a>
    </li>
    <li class:selected={page === "about"}>
      <a href="#about" on:click={() => setPage("about")}>About</a>
    </li>
    <li class:selected={page === "projects"}>
      <a href="#projects" on:click={() => setPage("projects")}>Projects</a>
    </li>
    <li class:selected={page === "contact"}>
      <a href="#contact" on:click={() => setPage("contact")}>Contact</a>
    </li>
  </ul>
</nav>

<style>
  nav {
    position: fixed;
    top: 0;
    right: 0;
    margin-right: 12px;
    z-index: 999999999999;

    @media only screen and (max-width: 768px) {
      display: none;
    }
  }

  li {
    list-style: none;
    color: #d6e4e5;
  }

  li:hover {
    color: #f6b17a;
  }

  .selected {
    color: #f6b17a;
  }

  ul {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  a {
    text-decoration: none;
    color: inherit;
    font-weight: 600;
    font-size: 1.2rem;
  }
</style>
