<script>
  import Heading from './Heading.svelte';
  import Animate from './Animate.svelte';

  const links = [
    {
      text: 'View CV',
      url: 'https://drive.google.com/file/d/1025ja3ser6s5GgM5G2Btenl25hoAtggZ/view',
      icon: '<svg class="h-6 transition" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6"><path d="M5.625 1.5c-1.036 0-1.875.84-1.875 1.875v17.25c0 1.035.84 1.875 1.875 1.875h12.75c1.035 0 1.875-.84 1.875-1.875V12.75A3.75 3.75 0 0016.5 9h-1.875a1.875 1.875 0 01-1.875-1.875V5.25A3.75 3.75 0 009 1.5H5.625z" /><path d="M12.971 1.816A5.23 5.23 0 0114.25 5.25v1.875c0 .207.168.375.375.375H16.5a5.23 5.23 0 013.434 1.279 9.768 9.768 0 00-6.963-6.963z" /</svg>',
    },
    {
      text: 'LinkedIn',
      url: 'https://linkedin.com/in/jameshollos',
      icon: '<svg class="h-6 transition" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" fill="currentColor" > <text>LinkedIn</text> <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z" /> </svg>',
    },
    {
      text: 'Email me',
      url: 'mailto:hollosj99@gmail.com',
      icon: '<svg class="h-6 transition" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"stroke-width="1.5" stroke="currentColor"><path stroke-linecap="round" d="M16.5 12a4.5 4.5 0 11-9 0 4.5 4.5 0 019 0zm0 0c0 1.657 1.007 3 2.25 3S21 13.657 21 12a9 9 0 10-2.636 6.364M16.5 12V8.25"/></svg>',
    },
    {
      text: 'GitHub',
      url: 'https://github.com/HollosJ',
      icon: '<svg class="h-6 transition fill-current" role="img"viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><text>GitHub</text><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>',
    },
  ];
</script>

<div class="grid gap-4">
  <Heading>Get In Touch</Heading>

  <div
    class="grid items-center content-center gap-4 sm:grid-cols-2 md:grid-cols-4"
  >
    {#each links as link}
      <Animate>
        <a href={link.url} class="button">
          <span>{@html link.icon}</span>

          <span>{link.text}</span>
        </a>
      </Animate>
    {/each}
  </div>
</div>
