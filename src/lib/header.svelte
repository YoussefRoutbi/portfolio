<script>
  const base = import.meta.env.BASE_URL;
  import { fly } from 'svelte/transition';
  import { onMount, onDestroy } from 'svelte';
  import { tweened } from 'svelte/motion';
  import { cubicInOut } from 'svelte/easing';

  let showComponent = false;
  let element;

  onMount(() => {
    const observer = new IntersectionObserver(
      ([entry]) => {
        if (entry.isIntersecting) {
          showComponent = true;
          observer.disconnect();
        }
      },
      { threshold: 0.4 }
    );

    if (element) observer.observe(element);
    onDestroy(() => {
      if (observer) observer.disconnect();
    });
  });

  let tech = tweened(0, { duration: 3000, easing: cubicInOut });
  let done_tech = false;
  onMount(() => { tech.set(11); });
  tech.subscribe(value => { if (Math.floor(value) === 11) done_tech = true; });

  let proj = tweened(0, { duration: 3000, easing: cubicInOut });
  let proj_done = false;
  onMount(() => { proj.set(7); });
  proj.subscribe(value => { if (Math.floor(value) === 7) proj_done = true; });

  let cod = tweened(0, { duration: 3000, easing: cubicInOut });
  let done_cod = false;
  onMount(() => { cod.set(4); });
  cod.subscribe(value => { if (Math.floor(value) === 4) done_cod = true; });
</script>

<header class="text-white py-5" id="home">
  <nav class="navbar navbar-expand-lg navbar-light pb-3">
    <div class="container-fluid align-items-center">
      <h3><a href="mailto:youssef.rouatbi17@gmail.com" class="text-decoration-none text-light nav-link ms-3">Youssef Rouatbi</a></h3>
      <button class="navbar-toggler text-light" type="button" data-bs-toggle="collapse" data-bs-target="#menu" aria-controls="menu" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse justify-content-end" id="menu">
        <ul class="navbar-nav align-items-center gap-2 gap-lg-3 me-3">
          <li class="nav-item"><a href="#home" class="nav-link text-light fw-semibold">Home</a></li>
          <li class="nav-item"><a href="#project" class="nav-link text-light fw-semibold">Portfolio</a></li>
          <li class="nav-item"><a href="#contact" class="nav-link text-light fw-semibold">Apply</a></li>
          <li class="nav-item d-lg-none"><a href="#contact" class="nav-link text-light fw-semibold">Contact</a></li>
          <li class="nav-item d-none d-lg-block">
            <a href="mailto:youssef.rouatbi17@gmail.com">
              <button class="btn btn-primary px-4 py-2 rounded-5 fw-bold">Contact Me</button>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
  <hr class="border-light">

  <main class="container py-5">
    <div class="row align-items-center gy-4">
      <!-- LEFT COLUMN -->
      <div class="col-lg-5 text-center text-lg-start position-relative">
        <div bind:this={element}>
          {#if showComponent}
            <h1 class="fw-bold mb-4" in:fly={{ x: -100, opacity: 0, duration: 1000 }} out:fly={{ x: 100, opacity: 0, duration: 600 }}>
              Hi, I'm <span class="text-primary">Youssef Rouatbi</span><br/>Full Stack Developer & Designer
            </h1>
            <p class="lead mb-4" style="max-width:600px;" in:fly={{ x: -100, opacity: 0, duration: 1200 }} out:fly={{ x: 100, opacity: 0, duration: 600 }}>
              Crafting modern, responsive websites with passion and precision.
            </p>
            <a href="#contact" class="btn btn-outline-primary rounded-pill px-4 py-2 fw-semibold" in:fly={{ x: -100, opacity: 0, duration: 1300 }} out:fly={{ x: 100, opacity: 0, duration: 600 }}>Get in Touch</a>
          {/if}
        </div>

        <!-- BACKGROUND IMAGES -->
        <img src="{base}pictures/code.svg" alt="Code Icon" class="position-absolute top-0 start-50 translate-middle-x opacity-25" style="width:300px; pointer-events:none; z-index:-1; animation: floatUpDown 4s ease-in-out infinite;">
        <img src="{base}pictures/infos.svg" alt="Info Icon" class="position-absolute top-50 start-50 translate-middle opacity-25" style="width:300px; pointer-events:none; z-index:-1; animation: floatUpDown 4s ease-in-out infinite;">
      </div>

      <!-- RIGHT COLUMN -->
      <div class="col-lg-3 d-none d-lg-block position-relative">
        <div class="ms-5">
          <img src="{base}pictures/logos.svg" alt="Logos" class="img-fluid opacity-25">
        </div>
      </div>
    </div>
  </main>

  <!-- STATS CARDS -->
  <div class="container py-4">
    <div class="row justify-content-center gy-3">
      <div class="col-6 col-md-4 col-lg-3">
        <div class="card bg-transparent border-0 text-center shadow-sm rounded-pill">
          <div class="card-header text-white pt-2">
            <h5>Technologies Learning & Exploring</h5>
          </div>
          <div class="card-body">
            <h1 class="text-white">{Math.floor($tech)}{done_tech ? ' +' : ''}</h1>
          </div>
        </div>
      </div>

      <div class="col-6 col-md-4 col-lg-3">
        <div class="card bg-transparent border-0 text-center shadow-sm rounded-pill">
          <div class="card-header text-white pt-2">
            <h5>Projects I've Built</h5>
          </div>
          <div class="card-body">
            <h1 class="text-white">{Math.floor($proj)}{proj_done ? ' +' : ''}</h1>
          </div>
        </div>
      </div>

      <div class="col-6 col-md-4 col-lg-3">
        <div class="card bg-transparent border-0 text-center shadow-sm rounded-pill">
          <div class="card-header text-white pt-2">
            <h5>Passion for Coding</h5>
          </div>
          <div class="card-body">
            <h1 class="text-white">{Math.floor($cod)}{done_cod ? ' +' : ''}</h1>
          </div>
        </div>
      </div>
    </div>
  </div>
</header>

<style>
  header { color: white; }
  main { min-height: 75vh; }

  @keyframes floatUpDown {
    0%,100% { transform: translateY(0); }
    50% { transform: translateY(-20px); }
  }

  /* Cards shadow */
  .card { box-shadow: 2px 2px 5px 2px #015a86b4; }
</style>
