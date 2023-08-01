<script>
  import { onMount } from 'svelte';
  import { createClient } from 'contentful';

  import Heading from './Heading.svelte';
  import Modal from './Modal.svelte';

  let projects = [];

  let loading = true;

  const client = createClient({
    space: import.meta.env.CONTENTFUL_SPACE_ID,
    accessToken: import.meta.env.CONTENTFUL_API_KEY,
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
      <button
        class={`relative group md:hover:rotate-1 overflow-hidden md:hover:shadow-2xl shadow-md md:hover:shadow-black/50 dark:md:hover:shadow-white/50 pointer-events-auto transition-all md:hover:scale-105 duration-300 md:hover:opacity-100 md:group-hover:[&:not(:hover)]:opacity-25`}
        on:click={() => handleOpen(key)}
        aria-label={`View ${project.title}`}
      >
        <img
          class="object-cover w-full aspect-video"
          width="200"
          height="200"
          src={project.image.fields.file.url}
          alt={project.title}
        />
      </button>
    {/each}
  </div>
</div>

<Modal bind:open={showModal} project={projects[currentIndex]} />
