<script>
  const logos = [
    'contentful','unilever','stackoverflow','riot','nike','kubernetes','figma'
  ];
  const base = import.meta.env.BASE_URL;
</script>

<section class="clients-section py-5">
  <div class="slider-wrapper">
    <div class="slider">
      {#each logos as logo}
        <img src="{base}pictures/{logo}.png" alt="{logo}" />
      {/each}
      {#each logos as logo} <!-- duplicate for seamless loop -->
        <img src="{base}pictures/{logo}.png" alt="{logo}" />
      {/each}
    </div>
  </div>
</section>

<style>
.clients-section {
  width: 100%;
  overflow: hidden;
  background-color: #0a0a0a;
  padding: 2rem 0;
}

.slider-wrapper {
  overflow: hidden;
  width: 100%;
}

.slider {
  display: flex;
  gap: 4rem;
  animation: scroll 20s linear infinite;
}

.slider img {
  height: 60px;
  width: auto;
  object-fit: contain;
  flex-shrink: 0;
}

/* Continuous scroll animation */
@keyframes scroll {
  0% { transform: translateX(0); }
  100% { transform: translateX(-50%); } /* scroll half since we duplicated logos */
}

/* Responsive adjustments */
@media (max-width: 992px) {
  .slider img {
    height: 50px;
  }
  .slider {
    gap: 2rem;
    animation-duration: 15s;
  }
}

@media (max-width: 576px) {
  .slider img {
    height: 40px;
  }
  .slider {
    gap: 1.5rem;
    animation-duration: 12s;
  }
}
</style>
