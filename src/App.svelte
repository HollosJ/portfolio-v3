<script>
  import { onMount } from 'svelte';

  import Hero from './lib/components/Hero.svelte';
  import About from './lib/components/About.svelte';
  import Skills from './lib/components/Skills.svelte';
  import Projects from './lib/components/Projects.svelte';
  import Contact from './lib/components/Contact.svelte';
  import Footer from './lib/components/Footer.svelte';

  let isDarkMode = false;

  function toggleDarkMode() {
    isDarkMode = !isDarkMode;
    localStorage.setItem('darkMode', JSON.stringify(isDarkMode));
    document.body.classList.toggle('dark', isDarkMode);
  }

  onMount(() => {
    // If local storage contains an item for dark mode, update state and add dark class to the body, if not - add it
    const storedDarkMode = localStorage.getItem('darkMode');
    if (storedDarkMode) {
      isDarkMode = JSON.parse(storedDarkMode);
      document.body.classList.toggle('dark', isDarkMode);
    } else {
      const prefersDarkMode = window.matchMedia(
        '(prefers-color-scheme: dark)'
      ).matches;
      isDarkMode = prefersDarkMode;
      localStorage.setItem('darkMode', JSON.stringify(isDarkMode));
      document.body.classList.toggle('dark', isDarkMode);
    }
  });
</script>

<div
  class={`font-mono bg-gradient-to-tr from-slate-200 to-white dark:text-white dark:from-black bg-fixed dark:to-neutral-900 transition-colors selection:bg-pink-600 selection:text-black relative`}
  id="app"
>
  <Hero />

  <div class="container grid gap-8 transition md:max-w-screen-md md:gap-16">
    <About />

    <Skills />

    <Projects />

    <Contact />
  </div>

  <Footer {toggleDarkMode} {isDarkMode} />
</div>
