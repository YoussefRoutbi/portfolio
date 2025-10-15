<script>
  import { onMount } from 'svelte';
  import { fly } from 'svelte/transition';
  import AOS from 'aos';

  let showSkills = false;

  onMount(() => {
    AOS.init({ duration: 1000 });
    setTimeout(() => {
      showSkills = true;
    }, 200);
  });
</script>

<section id="project" class="text-light py-5 mb-5 px-5 container-fluid" data-aos="fade-right">
  <div class="row justify-content-center">
    <!-- LEFT TEXT SIDE -->
    <div class="col-12 col-lg-4 ms-5">
      <h1 class="mt-2" in:fly={{ y: -100, opacity: 0.3, duration: 1000 }}>
        <span style="color: #00aaff;">A collection of my favorite web projects</span>
      </h1>
      <br />
      <p class="fs-4 fw-semibold" in:fly={{ y: -100, opacity: 0.3, duration: 1000 }}>
        From dynamic dashboards to sleek portfolio sites. Each project highlights my skills in Svelte, JavaScript,
        CSS, and responsive design. Built with clean code, cool animations, and real-world usability in mind.
      </p>
      <br /><br />
      <p class="fs-4 fw-semibold">Do you want the same?</p>
      <button
        class="btn btn-primary mt-4 rounded-5 p-3 fw-semibold text-center"
        in:fly={{ y: -100, opacity: 0.3, duration: 1000 }}
      >
        Apply me <i class="bi bi-envelope-fill"></i>
      </button>
    </div>

    <!-- PROJECT CARDS -->
    <div class="col-12 col-lg-7 pt-5">
      <!-- Normal layout on desktop -->
      <div class="d-none d-lg-flex flex-wrap justify-content-end cards-desktop">
        {#each Array(4) as _, i}
          <div class="card text-white p-3 mb-4 me-4" style="width: 40%;" data-aos="fade-up">
            <div class="card-header"></div>
            <div class="card-body d-flex justify-content-center flex-wrap gap-2">
              <div class="icons bg-primary"><p>HTML</p></div>
              <div class="icons bg-primary"><p>CSS</p></div>
              <div class="icons bg-primary"><p>JavaScript</p></div>
              <div class="icons bg-primary"><p>Bootstrap</p></div>
              <div class="icons bg-primary"><p>PHP</p></div>
            </div>
            <p class="text-primary mt-3 see">
              <a href="#" class="text-decoration-none">
                <i class="bi bi-box-arrow-up-right" style="font-size: 1.5rem;"></i> See more
              </a>
            </p>
          </div>
        {/each}
      </div>

      <!-- Horizontal scroll for mobile/tablet -->
      <div class="d-flex d-lg-none project-slider">
        {#each Array(4) as _, i}
          <div class="card text-white p-3 me-3" style="min-width: 80%;" data-aos="fade-up">
            <div class="card-header"></div>
            <div class="card-body d-flex justify-content-center flex-wrap gap-2">
              <div class="icons bg-primary"><p>HTML</p></div>
              <div class="icons bg-primary"><p>CSS</p></div>
              <div class="icons bg-primary"><p>JavaScript</p></div>
              <div class="icons bg-primary"><p>Bootstrap</p></div>
              <div class="icons bg-primary"><p>PHP</p></div>
            </div>
            <p class="text-primary mt-3 see">
              <a href="#" class="text-decoration-none">
                <i class="bi bi-box-arrow-up-right" style="font-size: 1.5rem;"></i> See more
              </a>
            </p>
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>

<style>
  section {
    height: max-content;
    padding: 5rem 2rem;
    margin-top: 10%;
  }

  .card {
    height: 400px;
    overflow: hidden;
    cursor: pointer;
    position: relative;
    background: transparent;
    box-shadow: 2px 2px 2px 2px rgba(1, 90, 134, 0.363);
    border-radius: 12px;
  }

  .card-header {
    height: 250px;
    background-image: url('./me.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    border-radius: 0.5rem 0.5rem 0 0;
  }

  .icons {
    width: 90px;
    height: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 8px;
  }

  .icons p {
    font-size: 15px;
    margin: 0;
    font-weight: 500;
  }

  .see {
    font-size: 20px;
    font-weight: bold;
  }

  /* 🔹 Mobile/Tablet Horizontal Scroll */
  .project-slider {
    overflow-x: auto;
    display: flex;
    scroll-snap-type: x mandatory;
    -webkit-overflow-scrolling: touch;
    padding-bottom: 1rem;
  }

  .project-slider::-webkit-scrollbar {
    display: none;
  }

  .project-slider .card {
    scroll-snap-align: start;
    flex-shrink: 0;
  }
</style>
