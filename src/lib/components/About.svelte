<script>
  import Heading from './Heading.svelte';
  import Animate from './Animate.svelte';
  import ViewCVCTA from './ViewCVCTA.svelte';
</script>

<div id="about" class="grid gap-4 sm:text-xl scroll-mt-16">
  <Heading>About Me</Heading>

  <Animate>
    <p>
      Hey there! 👋 I'm James, a front-end developer based in the North-West of
      England. I love the art of crafting exceptional web experiences using the
      latest technologies.
    </p>
  </Animate>

  <Animate>
    <p>
      💪 With a strong foundation in HTML, CSS, and JavaScript, I enjoy
      exploring different technologies and tools like PHP, Tailwind CSS,
      Alpine.js, and WordPress. By leveraging these technologies, I can create
      dynamic and visually stunning websites.
    </p>
  </Animate>

  <Animate>
    <p>
      💼 In my most recent position as a developer at <a
        class="font-bold text-pink-500 transition hover:text-jurple shadow-white"
        href="https://onlinemortgageadvisor.co.uk"
        target="_blank"
        rel="noopener">OMA</a
      >, I was using such technologies as PHP, Tailwind, Alpine.js, WordPress
      and sometimes more modern and exciting tooling such as Svelte and Astro.
    </p>
  </Animate>

  <div class="justify-self-center">
    <Animate>
      <ViewCVCTA wiggle={true} />
    </Animate>
  </div>
</div>
