<script>
  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';

  let isVisible = false;
  let parent;

  onMount(() => {
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        isVisible = entry.isIntersecting;
      });
    });

    observer.observe(parent);
  });
</script>

<div bind:this={parent}>
  {#if isVisible}
    <div transition:fade={{ duration: 250, delay: 100 }}>
      <slot />
    </div>
  {/if}
</div>
