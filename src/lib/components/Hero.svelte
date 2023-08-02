<script>
  const jumpToContent = () => {
    document.querySelector('#about').scrollIntoView({ behavior: 'smooth' });
  };

  import Me from '../../assets/me.webp';
  import Image from './Image.svelte';
  import Button from './Button.svelte';
</script>

<div class="container relative grid gap-16 py-16 md:py-24 md:max-w-screen-md">
  <div class="grid gap-4 md:gap-8 justify-items-center md:grid-cols-2">
    <!-- Text -->
    <div
      class="relative grid content-center gap-4 text-lg text-center md:gap-8 md:text-right"
    >
      <div class="grid">
        <p class="relative">Hi! I'm</p>

        <h1
          class="text-4xl font-black text-transparent bg-clip-text md:text-7xl bg-gradient-to-r from-jurple to-pink-600"
        >
          James Hollos
        </h1>

        <span>Front-end Developer</span>
      </div>

      <div class="grid grid-cols-2 gap-2 md:flex md:justify-end">
        <Button
          href="https://drive.google.com/file/d/1025ja3ser6s5GgM5G2Btenl25hoAtggZ/view"
          class="text-sm hover:border-black">Download CV</Button
        >

        <Button
          href="mailto:hollosj99@gmail.com"
          class="text-sm hover:border-black">Email Me</Button
        >
      </div>
    </div>

    <!-- Headshot -->
    <div
      class="relative flex max-w-[200px] md:max-w-[300px] md:justify-self-start aspect-square group"
    >
      <div
        class="absolute w-full h-full transition shadow-2xl left-2 top-2 -z-0 bg-gradient-to-tr from-jurple to-pink-600"
      />

      <Image
        class="relative h-full transition md:group-hover:-translate-x-1 md:grayscale md:group-hover:grayscale-0 md:group-hover:-translate-y-1"
        src={Me}
        width="500"
        height="500"
        alt="Me"
      />
    </div>
  </div>

  <!-- Jump link -->
  <button
    class="group bottom-4 left-1/2 justify-self-center"
    on:click={jumpToContent}
    aria-label="Jump to content"
  >
    <div
      class="flex items-center justify-center w-12 h-12 font-bold transition-colors border-2 border-black cursor-pointer dark:border-white animate-bounce group-hover:border-jurple group-hover:text-jurple"
      aria-label="Scroll Down"
    >
      &#8595;
    </div>
  </button>
</div>
