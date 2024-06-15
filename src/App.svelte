<script lang="ts">
  import About from "./lib/About.svelte"
  import Contact from "./lib/Contact.svelte"
  import Hero from "./lib/Hero.svelte"
  import Navbar from "./lib/ui/Navbar.svelte"
  import Section from "./lib/ui/Section.svelte"
  import SectionBackground from "./lib/ui/SectionBackground.svelte"
</script>

<main>
  <Hero />
  <Navbar />

  <SectionBackground />

  <About />

  <Section id={"projects"} title={"Projects"}>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras a sagittis tellus. Nulla
    congue tristique hendrerit. Class aptent taciti sociosqu ad litora torquent per
    conubia nostra, per inceptos himenaeos. Etiam luctus tincidunt elementum. Praesent
    tincidunt vulputate sollicitudin. Fusce hendrerit mattis est vel congue. Donec
    lacinia, ipsum eget imperdiet egestas, lectus massa sagittis augue, sit amet maximus
    tortor augue a nisi. Suspendisse ut vehicula leo. Quisque ut est magna. Aenean et
    dolor lectus. Cras ac libero ac ex volutpat gravida. Nulla condimentum, arcu sed
    lacinia aliquam, est nunc congue leo, et cursus sapien odio quis diam. Maecenas nec
    sollicitudin felis. Pellentesque ullamcorper elit leo, id consectetur est consequat
    sed. Fusce vehicula nulla at sem iaculis sollicitudin. Proin placerat risus id metus
    ullamcorper gravida. Nulla facilisi. Vestibulum volutpat tempus est, vitae elementum
    mauris vulputate in. Pellentesque egestas, ipsum et cursus varius, urna erat laoreet
    urna, vel aliquam turpis mauris lacinia erat. Cras blandit sagittis sapien, vitae
    efficitur nibh interdum ut. Pellentesque mollis lorem libero, eget ultrices ligula
    imperdiet eget. Quisque fringilla imperdiet condimentum. Nunc facilisis, odio nec
    ornare placerat, leo metus iaculis urna, vitae volutpat neque augue sit amet mauris.
    Donec a est fringilla, rhoncus eros nec, feugiat nibh. Vivamus vel placerat metus.
    Etiam eget arcu quis felis vestibulum commodo. Cras auctor, sem sed placerat blandit,
    sem nulla sodales lorem, vitae sagittis urna est in nisl. Maecenas ut viverra felis.
    Suspendisse nec luctus justo. Donec ornare efficitur arcu vitae efficitur. Nullam orci
    nulla, faucibus et porta in, euismod et metus. Etiam a metus arcu. Duis massa lectus,
    mattis laoreet eleifend et, facilisis eu nisi. Morbi sed sapien vitae justo fringilla
    mattis non eget mauris. Quisque quis nunc sed urna euismod accumsan. Praesent sit amet
    elit tristique sem laoreet mollis. Duis vitae turpis sit amet velit accumsan dapibus
    eu sit amet felis. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Class
    aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.
    Etiam tempor arcu id efficitur porta. Mauris a tellus ac metus ultricies mattis. Etiam
    ac ullamcorper tortor. Duis porttitor tortor sed est cursus, id mattis diam commodo.
    Cras facilisis volutpat nisi et placerat. Nunc euismod viverra lacus id suscipit. Duis
    vehicula tortor egestas mi feugiat porta. Nullam suscipit libero a lacus efficitur
    elementum. Donec est lacus, consectetur non orci vitae, consequat luctus odio. Integer
    vestibulum magna in diam pretium, vitae mollis odio ultricies. Vestibulum feugiat
    nulla nibh, ultricies cursus mauris maximus sed.
  </Section>

  <Contact />
</main>
