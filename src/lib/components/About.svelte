<script>
  import Heading from './Heading.svelte';
  import ViewCVCTA from './ViewCVCTA.svelte';
</script>

<div id="about" class="grid gap-4 sm:text-xl">
  <Heading>About Me</Heading>

  <p>
    Hey there! 👋 I'm James, a front-end developer based in the North-West of
    England. I love the art of crafting exceptional web experiences using the
    latest technologies.
  </p>

  <p>
    💪 With a strong foundation in HTML, CSS, and JavaScript, I enjoy exploring
    different technologies and tools like PHP, Tailwind CSS, Alpine.js, and
    WordPress. By leveraging these technologies, I can create dynamic and
    visually stunning websites.
  </p>

  <p>
    💼 I'm currently working as a developer at <a
      class="font-bold text-pink-500 transition hover:text-jurple shadow-white"
      href="https://onlinemortgageadvisor.co.uk"
      target="_blank"
      rel="noopener">OMA</a
    >. Here I am using such technologies as PHP, Tailwind, Alpine.js, WordPress
    and sometimes more exciting tooling such as Svelte and Astro.
  </p>

  <ViewCVCTA wiggle={true} />
</div>
