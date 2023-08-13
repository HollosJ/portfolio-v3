<script>
  import { onMount } from 'svelte';

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

<div
  class={`${
    isVisible ? 'opacity-100' : 'opacity-0 pointer-events-none'
  } transition duration-500 delay-100`}
  bind:this={parent}
>
  <slot />
</div>
