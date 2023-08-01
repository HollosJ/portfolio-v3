<script>
  import Heading from './Heading.svelte';

  const svgs = {
    alpinejs:
      '<svg stroke="currentColor" fill="currentColor" stroke-width="0" role="img" viewBox="0 0 24 24" class="icon" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><title></title><path d="m24 12-5.72 5.746-5.724-5.741 5.724-5.75L24 12zM5.72 6.254 0 12l5.72 5.746h11.44L5.72 6.254z"></path></svg>',
  };

  const skills = [
    { icon: 'devicon-html5-plain', name: 'HTML' },
    { icon: 'devicon-css3-plain', name: 'CSS' },
    { icon: 'devicon-javascript-plain', name: 'JavaScript' },
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
    {
      icon: 'devicon-vscode-plain',
      name: 'VS Code',
    },
  ];
</script>

<div class="grid gap-4">
  <Heading>Skills</Heading>

  <div class="grid grid-cols-3 gap-4 md:grid-cols-5">
    {#each skills as skill}
      <!-- Skill -->
      <div class="grid transition-all justify-items-center group">
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

        <div class="w-16 h-[2px] skew-x-2 overflow-hidden">
          <div
            class="w-full h-full transition-all bg-gradient-to-r origin-right from-jurple to-pink-500 group-hover:scale-[1.50]"
          />
        </div>

        <!-- Name -->
        <span>{skill.name}</span>
      </div>
    {/each}
  </div>
</div>
