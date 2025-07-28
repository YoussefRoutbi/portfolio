<script>
  import { onMount } from 'svelte';
  import { fly } from 'svelte/transition';
  import AOS from 'aos';

  let shoWSkills = false;

  onMount(() => {
     AOS.init({
      duration: 1000
    });
    setTimeout(() => {
      shoWSkills = true;
    }, 200);
  });
</script>

<section id="project" class="d-none d-lg-block text-light py-5 mb-5 px-5 container-fluid" data-aos="fade-right">
  <div class="row justify-content-center">
    <div class="col-12 col-lg-4 ms-5" >
      <h1 class="mt-2" in:fly = {{y: -100, opacity: 0.3, duration: 1000}}>
        <span style="color: #00aaff;">A collection of my favorite web projects</span></h1><br>
        <p class=" fs-4 fw-semibold" in:fly = {{y: -100, opacity: 0.3, duration: 1000}}>from dynamic dashboards to sleek portfolio sites. Each project highlights my skills in Svelte, JavaScript, CSS,
        and responsive design. Built with clean code, cool animations, and real-world usability in mind.</p><br><br>
        <p class=" fs-4 fw-semibold">Do u want the same ?</p>
      <button class="btn btn-primary mt-4 rounded-5 p-3 w-25 fw-semibold text-center" in:fly = {{y: -100, opacity: 0.3, duration: 1000}}>Apply me <i class="bi bi-envelope-fill"></i></button>
    </div>

    <div class="col-12 col-lg-6 cards pt-5">
      <div class="d-flex flex-wrap justify-content-center justify-content-lg-end" data-aos="fade-up">

        <div class="card text-white p-3" style="width: 40%;">
          <div class="card-header"></div>
          <div class="card-body d-flex justify-content-center flex-wrap gap-2">
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="fw-semibold">Html</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="fw-semibold">Css</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="fw-semibold">JavaScript</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="fw-semibold">Bootstrap</p></div>
          </div>
          <p class="text-primary mt-3 see"><a href="#" class="text-decoration-none"><i class="bi bi-box-arrow-up-right" style="font-size: 1.5rem;"></i> See more</a></p>
        </div>

        <div class="card text-white p-3 mb-4 ms-5" style="width: 40%;" data-aos="fade-up">
          <div class="card-header"></div>
          <div class="card-body d-flex justify-content-center flex-wrap gap-2">
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Html</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Css</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">JavaScript</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Bootstrap</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Php</p></div>
          </div>
          <p class="text-primary mt-3 see"><a href="#" class="text-decoration-none"><i class="bi bi-box-arrow-up-right" style="font-size: 1.5rem;"></i> See more</a></p>
        </div>
        <div class="card text-white p-3 mb-4 ms-5" style="width: 40%;" data-aos="fade-up">
          <div class="card-header"></div>
          <div class="card-body d-flex justify-content-center flex-wrap gap-2">
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Html</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Css</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">JavaScript</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Bootstrap</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Php</p></div>
          </div>
          <p class="text-primary mt-3 see"><a href="#" class="text-decoration-none"><i class="bi bi-box-arrow-up-right" style="font-size: 1.5rem;"></i> See more</a></p>
        </div>
        <div class="card text-white p-3 mb-4 ms-5" style="width: 40%;" data-aos="fade-up">
          <div class="card-header"></div>
          <div class="card-body d-flex justify-content-center flex-wrap gap-2">
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Html</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Css</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">JavaScript</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Bootstrap</p></div>
            <div class=" icons border-0 p-3 shadow-lg text-center rounded-4 bg-primary"><p class="tools">Php</p></div>
          </div>
          <p class="text-primary mt-3 see"><a href="#" class="text-decoration-none"><i class="bi bi-box-arrow-up-right" style="font-size: 1.5rem;"></i> See more</a></p>
        </div>

      </div>
    </div>
  </div>
</section>

<section class="d-block d-lg-none text-light py-5 mb-5 px-5 container-fluid" data-aos="fade-right">
  
</section>

<style>
  section {
    height: max-content;
    padding: 5rem 2rem;
    margin-top: 10%;
    
  }
  .cards{
    margin-left: 10%;
  }
  @media (max-width: 992px) {
    .card {
      width: 100% !important;
    }
  }
.card{
  height: 400px;
  overflow: hidden;
  cursor: pointer;
  position: relative;
  background: transparent;
  box-shadow: 2px 2px 2px 2px  rgba(1, 90, 134, 0.363);
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
  }
.icons p {
    font-size: 15px;
    margin: 0;
  }
  .see{
    font-size: 20px;
    font-weight: bold;
  }
  .tools{
    font-weight:500 ;
  }
</style>
