
<section class="mt-5 p-2 pt-5 mb-3">
    <div class="text-center skills-section" style="max-width: 800px; margin: 0 auto;">
  <h1 class="text-primary d-flex align-items-center justify-content-center gap-3" style="font-weight: 700; font-size: 3rem;">
    Skills
    <img src="./pictures/dart.png" alt="Dart Logo" class="skills-icon mb-2" />
  </h1>
  <p class="text-white fs-5" style="margin-top: 0.5rem;">
    The Skills, Tools, and Technologies I Specialize In:
  </p>
</div>

<div class="slider-wrapper">
    <div class="slider">
        <img src="/pictures/python.png" alt="img1" />
        <img src="/pictures/php.png" alt="img2" />
        <img src="/pictures/sql.png" alt="img3" />
        <img src="/pictures/github.png" alt="img4" />
        <img src="/pictures/npm.png" alt="img5" />
        <img src="/pictures/python.png" alt="img1" />
        <img src="/pictures/php.png" alt="img2" />
        <img src="/pictures/sql.png" alt="img3" />
        <img src="/pictures/github.png" alt="img4" />
        <img src="/pictures/npm.png" alt="img5" />
        <img src="/pictures/js.png" alt="img6" />
        <img src="/pictures/boot.png" alt="img7" />
        <img src="/pictures/svelte.png" alt="img8" />
        <img src="/pictures/html.png" alt="img9" />
        <img src="/pictures/css.png" alt="img10" />
        <img src="/pictures/js.png" alt="img6" />
        <img src="/pictures/boot.png" alt="img7" />
        <img src="/pictures/svelte.png" alt="img8" />
        <img src="/pictures/html.png" alt="img9" />
        <img src="/pictures/css.png" alt="img10" />
        
    </div>
</div>
</section>

<style>
    .slider-wrapper {
    overflow: hidden;
    width: 100%;
    max-width: 100vw;
    background: transparent;
}

.slider {
  display: flex;
  width: calc(1000px * 2);
  animation: scrollLeft 10s linear infinite;
}
.slider img {
  width: 200px;
  flex-shrink: 0;
}

@keyframes scrollLeft {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-1000px);
  }
}
.skills-icon {
  width: 64px;
  height: 64px;
  object-fit: contain;
}
.skills-section p {
  max-width: 500px;
  margin-left: auto;
  margin-right: auto;
  line-height: 1.4;
}

</style>