<script>
  import ProjectCard from "./ui/ProjectCard.svelte"
  import Section from "./ui/Section.svelte"
</script>

<Section id="projects" title="Projects">
  <ProjectCard
    name="Dev Finder"
    src="images/dev_finder.png"
    link="https://github.com/KSSidhu/dev-finder"
    variant="left"
    description="My take on a tutorial by WebDevCody to build a full-stack app to connect developers to work on projects collaboratively."
  />

  <ProjectCard
    name="Color Box"
    src="images/color_box.png"
    link="https://github.com/KSSidhu/colors-box-v2"
    description="A palette building SPA allowing users to build custom palettes for their projects."
    variant="right"
  />
</Section>
