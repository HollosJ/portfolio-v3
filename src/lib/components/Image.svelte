<script>
  import { onMount } from 'svelte';
  export let src, alt, width, height;

  let loaded = false;

  onMount(() => {
    const img = new Image();
    img.src = src;

    img.onload = () => {
      loaded = true;
    };
  });
</script>

{#if loaded}
  <img {src} {alt} {width} {height} class={`${$$props.class}`} />
{:else}
  <div class="w-full h-full bg-gray-300 animate-pulse" />
{/if}
