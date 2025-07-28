<script>
    const base = import.meta.env.BASE_URL;
  import { fly } from 'svelte/transition';
  import { onMount,onDestroy } from 'svelte';
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
  let tech = tweened(0,{ duration:3000, easing: cubicInOut});
  let done_tech = false;
  onMount(() => {
    tech.set(11);
  });
  tech.subscribe(value => {
    if (Math.floor(value) === 11) {
      done_tech = true;
    }
  });


  let proj = tweened(0, {duration:3000, easing: cubicInOut});
  let proj_done = false;

  onMount(() =>{
    proj.set(7);
  });
  proj.subscribe(value => {
    if(Math.floor(value) === 7){
        proj_done = true;
    }
  })
  
    let cod = tweened(0, {duration:3000, easing: cubicInOut});
    let done_cod = false;

  onMount(() =>{
    cod.set(4);
  });
  cod.subscribe(value => {
    if(Math.floor(value) === 4){
        done_cod = true;
    }
  })
</script>

<header class="text-center p-5" id="#home">
    
    <nav class="navbar navbar-expand-lg navbar-light pb-3" >
        <div class="container-fluid align-items-center">
            <h3><a href="mailto:youssef.rouatbi17@gmail.com" class="text-decoration-none text-light nav-link ms-5">Youssef Rouatbi</a></h3>
            <button class="navbar-toggler text-light mb-2" type="button" data-bs-toggle="collapse" data-bs-target="#menu" aria-controls="menu" aria-expanded="false" aria-label="toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse d-sm-flex justify-content-end" id="menu">
                <ul class="navbar-nav justify-content-end me-5 align-items-center gap-3">
                    <li class="nav-item">
                        <h5><a href="#home" class="nav-link text-light nvl">Home</a></h5>
                    </li>
                    <li class="nav-item">
                        <h5><a href="#project" class="nav-link text-light nvl">Portfolio</a></h5>
                    </li>
                    <li class="nav-item">
                        <h5><a href="#contact" class="nav-link text-light me-2 nvl">Apply</a></h5>
                    </li>
                    <li class="nav-item d-md-none">
                        <h5><a href="#contact" class="nav-link text-light nvl">Contact</a></h5>
                    </li>
                    <li class="nav-item d-none d-md-block button">
                        <a href="mailto:youssef.rouatbi17@gmail.com"><button class="btn btn-primary border-0 text-center px-4 py-2 rounded-5 fw-bold">Contact Me</button></a>
                    </li>
                </ul>
            </div>
        </div>
    </nav><hr>
    <main class="pt-5">
        <div class="row mt-5 gap-4">
            <div class="col-md-5 text-start">
                    <div bind:this={element}>
                        {#if showComponent}
                            <h1 class=" fw-bold mb-4" in:fly={{ x: -100, opacity: 0, duration: 1000 }} out:fly={{ x: 100, opacity: 0, duration: 600 }}>
                        Hi, I'm <span style="color: #00aaff;">Youssef Rouatbi</span><br/>Full Stack Developer & Designer</h1>
                        <p class="lead mb-5" style="max-width: 600px;" in:fly={{ x: -100, opacity: 0, duration: 1200 }} out:fly={{ x: 100, opacity: 0, duration: 600 }}>
                          Crafting modern, responsive websites with passion and precision.
                        </p>
                    
                        <a href="#contact" class="btn btn-outline-primary rounded-pill px-4 py-2 fw-semibold" in:fly={{ x: -100, opacity: 0, duration: 1300 }} out:fly={{x: 100, opacity: 0, duration: 600}}>Get in Touch</a>
                        {/if}
                    </div>
                    <img src="{base}pictures/code.svg" width="800" height="500" alt="Code Icon" class="symb z-0"/>
                    <img src="{base}pictures/infos.svg" alt="Code Icon" class="infos z-0"/>
            </div>
            <div class="col-md-3 d-none d-lg-block">
                <div class="codes ms-5 ps-5 position-relative">
                    <img src="{base}pictures/logos.svg" width="800" height="500" alt="Code Icon" class="bg-svg ms-5"/>
                </div>
            </div>
        </div>
    </main>
    <div class="container p-4">
        <div class="row d-felx align-items-center justify-content-between gap-5">
            <div class="col-6 col-md-3">
                <div class="card border border-0 rounded-pill px-2">
                    <div class="card-header text-white pt-2">
                        <h5>Technologies Learning & Exploring</h5>
                    </div>
                    <div class="card-body">
                        <h1 class="text-white">{Math.floor($tech)}{done_tech ? ' +' : ''}</h1>
                    </div>
                </div>
            </div>
            <div class="col-6 col-md-3">
                 <div class="card border border-0 rounded-pill px-2">
                    <div class="card-header text-white pt-2">
                        <h5>Project i've Built</h5>
                    </div>
                    <div class="card-body">
                        <h1 class="text-white">{Math.floor($proj)}{proj_done ? ' +' : ''}</h1>
                    </div>
                </div>
            </div>
            <div class="col-6 col-md-3">
                <div class="card border border-0 rounded-pill px-2">
                    <div class="card-header text-white pt-2">
                        <h5>Passion for coding</h5>
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
    header{
        color: white;
    }
    main{
        height: 75vh;
    }
    .navbar-nav {
        margin-right: 0;
    }
    .navbar-toggler {
        border-color: rgba(255, 255, 255, 0.5);
    }
    .button {
        position: relative;
        padding-left: 15px;
    }
    .button::before {
        content: '';
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        left: 0;
        height: 40px;
        border-left: 1px solid rgba(255, 255, 255, 0.568);
    }
    .nvl {
        position: relative;
        padding-bottom: 5px;
        transition: color 0.3s ease;
    }
    .nvl::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        height: 2px;
        width: 0;
        background-color: white;
        transition: width 0.3s ease;
    }
    .nvl:hover {
        color: #00aaff;
    }
    .nvl:hover::after {
        width: 100%;
    }
    main {
        max-width: 1140px;
        margin: 0 auto;
    }
    .codes img{
        opacity: 0.3;
        animation: floatUpDown 5s ease-in-out infinite reverse;
    }
    .col-md-5 {
        position: relative;
    }
    .symb {
        position: absolute;
        top: -40%;
        right: 60%;
        width: 500px;
        height: auto;
        opacity: 0.15;
        z-index: -1;
        pointer-events: none;
        animation: floatUpDown 4s ease-in-out infinite;
    }
    .infos {
        position: absolute;
        top: 40%;
        right: 50%;
        width: 500px;
        height: auto;
        opacity: 0.3;
        z-index: -1;
        pointer-events: none;
        animation: floatUpDown 4s ease-in-out infinite;
    }
    @media (max-width: 768px) {
        .symb{
        position: absolute;
        z-index: -15;
        opacity: 0.3;
        right: -21%;
        top: 30%;
        }
    }
    @keyframes floatUpDown {
    0%, 100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-20px);
    }
    }
    .card{
        background-color: transparent;
        width: 400px;
        box-shadow: 2px 2px 5px 2px #015a86b4;
    }
    .card p{
        font-size: 20px;
    }

</style>
