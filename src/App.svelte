<script>
  import { fade, fly } from 'svelte/transition';
  import Header from './lib/header.svelte';
  import Project from './lib/projects.svelte';
  import Skills from './lib/skills.svelte';
  import Contact from './lib/contact.svelte';
  import Blog from './lib/blog.svelte';
  import Footer from './lib/footer.svelte';

  let showAlert = false;

  function copyDiscord() {
    const username = "7aftour#8546";
    navigator.clipboard.writeText(username).then(() => {
      showAlert = true;
      setTimeout(() => (showAlert = false), 2500);
    });
  }
</script>

{#if showAlert}
  <div
    class="fixed-top text-center flex items-center mt-2 mx-auto gap-3 rounded-pill py-3 text-white shadow-lg z-50"
    style="background: #0a1930; width: 300px;"
    in:fade={{ duration: 200 }}
    out:fly={{ y: -10, duration: 200 }}
  >
    <i class="bi bi-check-circle-fill text-green-400 text-2xl"></i>
    <span class="fw-semibold text-base">Discord username copied!</span>
  </div>
{/if}

<Header />
<Skills />
<Project />
<Contact />
<Footer on:discordCopy={copyDiscord} />
