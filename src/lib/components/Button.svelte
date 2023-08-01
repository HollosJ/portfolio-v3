<script>
  export let href;
  export let style = 'outline-black hover:invert';

  let classes =
    'py-2 px-4 border-2 items-center justify-center transition flex text-center gap-2';

  if (style === 'outline-black') {
    classes = classes + ' border-black hover:bg-black hover:text-white';
  }

  if (style === 'outline-white') {
    classes =
      classes + ' border-white hover:bg-white text-white hover:text-black';
  }
</script>

<svelte:element
  this={href ? 'a' : 'button'}
  {href}
  class={`${classes} ${$$props.class}`}
>
  <slot />
</svelte:element>
