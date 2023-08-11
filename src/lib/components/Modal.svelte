<script>
  import { fade, blur } from 'svelte/transition';

  import Button from './Button.svelte';

  export let open;
  export let project;
</script>

{#if open}
  <div
    class="fixed top-0 left-0 z-50 flex items-center justify-center w-full h-screen isolate"
    transition:fade
  >
    <!-- Backdrop -->
    <button
      class="absolute top-0 left-0 z-0 w-full h-full bg-[#111]/75"
      on:click={() => (open = false)}
      aria-label="Backdrop"
    />

    <!-- Modal window -->
    <div
      class="relative z-10 grid content-start w-full h-full gap-4 p-4 text-center text-black md:h-auto md:max-w-screen-sm lg:max-w-screen-md bg-slate-50"
      transition:blur
    >
      <button
        class="absolute z-10 w-8 h-8 text-white bg-[#111] top-2 right-2 hover:bg-white hover:text-black transition"
        on:click={() => (open = false)}
        aria-label="Close button">&times;</button
      >

      <h3 class="font-bold justify-self-center">{project.title}</h3>

      <img
        class="justify-self-center"
        src={project.image.fields.file.url}
        alt={project.title}
        width="200"
        height="200"
      />

      <p>
        {@html project.description}
      </p>

      {#if project.workInProgress}
        <p>Work in progress 🔨</p>
      {/if}

      <!-- Links -->
      <div class="grid gap-4 sm:grid-cols-2">
        <Button href={project.livePreview} style="outline-black"
          ><svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            fill="currentColor"
            class="w-6 h-6"
          >
            <path
              fill-rule="evenodd"
              d="M2.25 5.25a3 3 0 013-3h13.5a3 3 0 013 3V15a3 3 0 01-3 3h-3v.257c0 .597.237 1.17.659 1.591l.621.622a.75.75 0 01-.53 1.28h-9a.75.75 0 01-.53-1.28l.621-.622a2.25 2.25 0 00.659-1.59V18h-3a3 3 0 01-3-3V5.25zm1.5 0v7.5a1.5 1.5 0 001.5 1.5h13.5a1.5 1.5 0 001.5-1.5v-7.5a1.5 1.5 0 00-1.5-1.5H5.25a1.5 1.5 0 00-1.5 1.5z"
              clip-rule="evenodd"
            />
          </svg>
          Live Preview</Button
        >

        <Button href={project.codePreview} style="outline-black"
          ><svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            fill="currentColor"
            class="w-6 h-6"
          >
            <path
              fill-rule="evenodd"
              d="M14.447 3.027a.75.75 0 01.527.92l-4.5 16.5a.75.75 0 01-1.448-.394l4.5-16.5a.75.75 0 01.921-.526zM16.72 6.22a.75.75 0 011.06 0l5.25 5.25a.75.75 0 010 1.06l-5.25 5.25a.75.75 0 11-1.06-1.06L21.44 12l-4.72-4.72a.75.75 0 010-1.06zm-9.44 0a.75.75 0 010 1.06L2.56 12l4.72 4.72a.75.75 0 11-1.06 1.06L.97 12.53a.75.75 0 010-1.06l5.25-5.25a.75.75 0 011.06 0z"
              clip-rule="evenodd"
            />
          </svg>

          Code</Button
        >
      </div>
    </div>
  </div>
{/if}
