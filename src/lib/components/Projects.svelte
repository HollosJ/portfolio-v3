<script>
  import { onMount } from 'svelte';
  import { createClient } from 'contentful';

  import Heading from './Heading.svelte';
  import Modal from './Modal.svelte';
  import Image from './Image.svelte';
  import Animate from './Animate.svelte';

  let projects = [];

  let loading = true;

  const client = createClient({
    space: import.meta.env.VITE_CONTENTFUL_SPACE_ID,
    accessToken: import.meta.env.VITE_CONTENTFUL_API_KEY,
  });

  onMount(async () => {
    try {
      const response = await client.getEntries({
        content_type: 'project',
        select: ['fields'],
      });
      projects = response.items.map((p) => {
        return p.fields;
      });

      loading = false;
    } catch (error) {
      console.error('Error retrieving projects:', error);
    }
  });

  let currentIndex = null;
  let showModal = false;

  const handleOpen = (key) => {
    currentIndex = key;
    showModal = true;
  };
</script>

<div class="grid gap-4">
  <Heading>My Work</Heading>

  <div
    class="grid gap-4 pointer-events-none sm:grid-cols-2 md:grid-cols-3 group md:gap-8"
  >
    <!-- Skeleton loaders -->
    {#if loading}
      <div class="w-full bg-gray-300 aspect-video animate-pulse" />

      <div class="w-full bg-gray-300 aspect-video animate-pulse" />

      <div class="w-full bg-gray-300 aspect-video animate-pulse" />
    {/if}

    {#each projects as project, key}
      <Animate>
        <button
          class={`${
            !project.image ? 'bg-black/10 dark:bg-white/10' : ''
          } group md:hover:rotate-1 w-full h-full grid items-center justify-center overflow-hidden md:hover:shadow-2xl shadow-md md:hover:shadow-black/50 dark:md:hover:shadow-white/50 pointer-events-auto transition-all md:hover:scale-105 duration-300 aspect-video md:hover:opacity-100 md:group-hover:[&:not(:hover)]:opacity-25`}
          on:click={() => handleOpen(key)}
          aria-label={`View ${project.title}`}
        >
          {#if project.image}
            <Image
              src={`${project.image.fields.file.url}?fm=webp`}
              alt={project.title}
              width="640"
              height="360"
              class="object-cover w-full aspect-video"
            />
          {:else}
            <div class="flex items-center h-full py-8">
              <span>{project.title}</span>
            </div>
          {/if}
        </button>
      </Animate>
    {/each}
  </div>
</div>

<Modal bind:open={showModal} project={projects[currentIndex]} />
