<script>
  import Heading from './Heading.svelte';

  const svgs = {
    alpinejs:
      '<svg stroke="currentColor" fill="currentColor" stroke-width="0" role="img" viewBox="0 0 24 24" class="icon" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><title></title><path d="m24 12-5.72 5.746-5.724-5.741 5.724-5.75L24 12zM5.72 6.254 0 12l5.72 5.746h11.44L5.72 6.254z"></path></svg>',
  };

  const skills = [
    { icon: 'devicon-html5-plain', name: 'HTML' },
    { icon: 'devicon-css3-plain', name: 'CSS' },
    { icon: 'devicon-javascript-plain', name: 'JS' },
    {
      icon: 'devicon-react-original',
      name: 'React',
    },
    {
      icon: 'devicon-sass-original',
      name: 'Sass',
    },
    { icon: 'devicon-tailwindcss-plain', name: 'Tailwind' },
    {
      name: 'AlpineJS',
      svg: svgs.alpinejs,
    },
    {
      icon: 'devicon-svelte-plain',
      name: 'Svelte',
    },
  ];
</script>

<div class="grid gap-4">
  <Heading>Skills</Heading>

  <div class="grid justify-between grid-cols-2 gap-4 md:gap-8 md:grid-cols-4">
    {#each skills as skill}
      <!-- Skill -->
      <div
        class="grid p-2 transition-all rounded bg-black/10 dark:bg-white/10 justify-items-center group"
      >
        <!-- Icon -->
        <div
          class="h-8 text-2xl transition-all group-hover:rotate-3 group-hover:scale-105"
        >
          {#if skill.svg}
            {@html skill.svg}
          {/if}

          {#if !skill.svg}
            <i class={`${skill.icon} shadow-2xl`} />
          {/if}
        </div>

        <!-- Name -->
        <span>{skill.name}</span>
      </div>
    {/each}
  </div>
</div>
