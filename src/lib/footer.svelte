<script>
    import { createEventDispatcher } from 'svelte';
    import AOS from 'aos';
    export let showAlert = false;
    const dispatch = createEventDispatcher();

    function handleDiscordClick() {
    dispatch('discordCopy'); 
  }

    let year = new Date().getFullYear();
</script>

<footer class="footer-section py-5" style="background: transparent;">
    <div class="container">
        <div class="row text-white" data-aos="fade-right">
            <div class="col-md-6 mb-4 mb-md-0">
                <h5 class="fw-bold mb-2" style="color: #3399ff;">Nice To Meet You</h5>
                <h2 class="fw-bold mb-3">Hi there, I’m Youssef Rouatbi</h2>
                <p>
                    I’ve been creating sleek, smart, and functional websites and web apps for the past 2 years. From dynamic dashboards to custom systems, I deliver clean code and solid solutions that keep my clients coming back.
                </p>
                <p>
                    I am passionate about creating and designing delightful experiences through a mix of business to keep customers and users happy with their products and services online.
                </p>
                <div class="d-flex align-items-center gap-2 mt-3">
                    <a href="mailto:youssef.rouatbi17@gmail.com" class="btn btn-primary btn-sm rounded-pill px-4">Contact Me</a>
                    <a href="https://www.facebook.com/youssef.rouatbi.709251" class="text-white fs-5 ms-2"><i class="bi bi-facebook"></i></a>
                    <a href="https://www.instagram.com/youssef__rouatbi/" class="text-white fs-5 ms-2"><i class="bi bi-instagram"></i></a>
                    <a href="#" class="text-white fs-5 ms-2" on:click|preventDefault={handleDiscordClick}><i class="bi bi-discord"></i></a>
                    <a href="https://wa.me/21621238808" class="text-white fs-5 ms-2"><i class="bi bi-whatsapp"></i></a>
                </div>
            </div>
            <div class="col-md-6">
                <h4 class="fw-bold mb-3">Frequently Asked Questions</h4>
                <div class="accordion accordion-flush custom-accordion" id="faqAccordion">
                    <div class="accordion-item bg-transparent border-0">
                        <h2 class="accordion-header" id="faq1">
                            <button class="accordion-button collapsed bg-transparent text-white fw-bold" type="button" data-bs-toggle="collapse" data-bs-target="#collapse1">
                                How many days does it take to develop a project ?
                            </button>
                        </h2>
                        <div id="collapse1" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
                            <div class="accordion-body text-white-50">
                                It depends on the project scope, but typically 1-3 weeks for most projects.
                            </div>
                        </div>
                    </div>
                    <div class="accordion-item bg-transparent border-0">
                        <h2 class="accordion-header" id="faq2">
                            <button class="accordion-button collapsed bg-transparent text-white fw-bold" type="button" data-bs-toggle="collapse" data-bs-target="#collapse2">
                                What is the budget for the project ?
                            </button>
                        </h2>
                        <div id="collapse2" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
                            <div class="accordion-body text-white-50">
                                The budget varies based on requirements. Contact me for a quote.
                            </div>
                        </div>
                    </div>
                    <div class="accordion-item bg-transparent border-0">
                        <h2 class="accordion-header" id="faq3">
                            <button class="accordion-button collapsed bg-transparent text-white fw-bold" type="button" data-bs-toggle="collapse" data-bs-target="#collapse3">
                                Can design edits be made during design time ?
                            </button>
                        </h2>
                        <div id="collapse3" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
                            <div class="accordion-body text-white-50">
                                Yes, design edits can be made during the design phase.
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row mt-5" data-aos="fade-up">
            <div class="col-12">
                <div class="rounded-4 py-5 px-3 text-center" style="background: rgba(51, 102, 255, 0.85);">
                    <h2 class="fw-bold mb-3 text-white">Get in touch</h2>
                    <p class="text-white-50 mb-4">
                        If you have a website or mobile app idea in mind or you need some advice about product design, feel free to contact me. Currently my time books quickly, authorities sooner you write, the better it is for both of us.
                    </p>
                    <a href="mailto:youssef.rouatbi17@gmail.com" class="btn btn-outline-light rounded-pill px-4">Contact Me</a>
                </div>
            </div>
        </div>
        <div class="text-center text-white-50 mt-4">
            &copy; {year} Youssef Rouatbi. All rights reserved.
        </div>
    </div>
</footer>
<style>
    .footer-section {
        background: transparent;
        margin-top: 20rem;
    }
    .accordion-button:focus {
        box-shadow: none;
    }
    .accordion-button:not(.collapsed) {
        color: #3399ff;
        background-color: transparent;
    }
    .custom-accordion {
        border: 2px solid var(--bs-primary);
        border-radius: 1rem;
        padding: 0.5rem;
        background: transparent;
    }
    .custom-accordion .accordion-item {
        border: none;
        background: transparent;
    }
    .custom-accordion .accordion-button {
        border-radius: 0.75rem !important;
        margin-bottom: 0.25rem;
    }
</style>