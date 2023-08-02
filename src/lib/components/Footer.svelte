<script>
  export let isDarkMode;
  export let toggleDarkMode;

  let date = new Date();
  let year = date.getFullYear();
</script>

<div class="py-2 mt-8 text-white bg-black">
  <div class="container flex items-center justify-center gap-2 text-center">
    <span>&copy; Copyright {year} James Hollos</span>

    <button
      class="relative w-6 h-6 overflow-hidden transition hover:opacity-75"
      on:click={toggleDarkMode}
      aria-label="Toggle dark mode"
    >
      <svg
        class={`w-full h-full absolute left-0 top-0 fill-yellow-300 transition transform duration-500 ${
          isDarkMode ? 'translate-y-[1.5rem]' : ''
        }`}
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 24 24"
        fill="currentColor"
      >
        <path
          d="M12 2.25a.75.75 0 01.75.75v2.25a.75.75 0 01-1.5 0V3a.75.75 0 01.75-.75zM7.5 12a4.5 4.5 0 119 0 4.5 4.5 0 01-9 0zM18.894 6.166a.75.75 0 00-1.06-1.06l-1.591 1.59a.75.75 0 101.06 1.061l1.591-1.59zM21.75 12a.75.75 0 01-.75.75h-2.25a.75.75 0 010-1.5H21a.75.75 0 01.75.75zM17.834 18.894a.75.75 0 001.06-1.06l-1.59-1.591a.75.75 0 10-1.061 1.06l1.59 1.591zM12 18a.75.75 0 01.75.75V21a.75.75 0 01-1.5 0v-2.25A.75.75 0 0112 18zM7.758 17.303a.75.75 0 00-1.061-1.06l-1.591 1.59a.75.75 0 001.06 1.061l1.591-1.59zM6 12a.75.75 0 01-.75.75H3a.75.75 0 010-1.5h2.25A.75.75 0 016 12zM6.697 7.757a.75.75 0 001.06-1.06l-1.59-1.591a.75.75 0 00-1.061 1.06l1.59 1.591z"
        />
      </svg>

      <svg
        class={`w-full h-full absolute left-0 top-0 fill-jurple transition transform duration-500 ${
          !isDarkMode ? 'translate-y-[1.5rem]' : ''
        }`}
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 24 24"
        fill="none"
      >
        <path
          fill-rule="evenodd"
          d="M9.528 1.718a.75.75 0 01.162.819A8.97 8.97 0 009 6a9 9 0 009 9 8.97 8.97 0 003.463-.69.75.75 0 01.981.98 10.503 10.503 0 01-9.694 6.46c-5.799 0-10.5-4.701-10.5-10.5 0-4.368 2.667-8.112 6.46-9.694a.75.75 0 01.818.162z"
          clip-rule="evenodd"
        />
      </svg>
    </button>
  </div>
</div>
