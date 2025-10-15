<script>
  import AOS from 'aos';
</script>

<section class="py-2 px-3" id="contact">
  <div class="container">
    <h1 class="text-center text-primary mb-5 fw-bold d-flex flex-wrap align-items-center justify-content-center display-3 display-md-2 display-sm-5">
      Let's Connect!
      <img src="https://www.mejdi.ch/emojis/envelope.png" class="ms-2 mb-2 img-fluid" alt="" data-aos="fade-right">
    </h1>

    <p class="text-center fw-bold d-flex align-items-center justify-content-center fs-2 fs-md-4 fs-sm-6 w-100 w-md-75 mx-auto mb-5 flex-wrap" data-aos="fade-right">
      Have a question, suggestion, or just want to chat? Shoot me a message using the contact form below, and I’ll get back to you in no time!
    </p>

    <form action="#" method="POST" class="mx-auto p-3 w-100 w-md-75 w-lg-50" data-aos="fade-up">

      <label for="name" class="form-label ms-2">Full Name:</label>
      <input type="text" id="name" class="form-control form-control-lg border rounded-pill p-3 border-primary mb-4" placeholder="Foulen el fouleni" required>

      <label for="email" class="form-label ms-2">Email Address:</label>
      <input type="email" id="email" class="form-control form-control-lg border rounded-pill p-3 border-primary mb-4" placeholder="example@gmail.com">

      <label for="service" class="form-label ms-2">Service:</label>
      <select name="service" id="service" class="form-select form-select-lg border rounded-pill p-3 border-primary mb-4" required>
        <option value="" class="text-primary">--Select a Service--</option>
        <option value="" class="text-primary">Front-end Website</option>
        <option value="" class="text-primary">Back-end Website</option>
        <option value="" class="text-primary">Full Stack Website</option>
      </select>

      <div class="form-floating msg">
        <textarea name="message" class="form-control form-control-lg border rounded-3 p-3 border-primary mb-4" id="message" cols="50" rows="5" placeholder="message..." required></textarea>
      </div>

      <button class="btn btn-outline-primary mt-4 w-100 rounded-5">Get in touch</button>
    </form>
  </div>
</section>

<style>
  section {
    min-height: 100vh;
    margin-top: 10rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  input,
  select,
  textarea {
    background-color: transparent;
    color: white;
  }

  select {
    background-color: transparent;
  }

  .form-control::placeholder {
    color: white;
  }

  .form-control:focus,
  .form-select:focus {
    background-color: transparent;
    color: white;
    box-shadow: none;
  }

  #message {
    resize: none;
    height: 150px;
    background-color: transparent;
    color: white;
  }

  #message::placeholder {
    color: white;
  }

  /* ✅ Responsive refinements */
  @media (max-width: 992px) {
    section {
      margin-top: 8rem;
      padding-bottom: 2rem;
    }

    h1 {
      font-size: 2.5rem;
    }

    p {
      font-size: 1.25rem;
      width: 90% !important;
    }

    form {
      width: 80% !important;
    }
  }

  @media (max-width: 768px) {
    h1 {
      font-size: 2rem;
    }

    p {
      font-size: 1.1rem;
    }

    form {
      width: 90% !important;
    }
  }

  @media (max-width: 480px) {
    h1 {
      font-size: 1.6rem;
      text-align: center;
      flex-direction: column;
    }

    p {
      font-size: 1rem;
      width: 100% !important;
    }

    form {
      width: 100% !important;
      padding: 1rem;
    }

    button {
      font-size: 1rem;
      padding: 0.75rem;
    }
  }
</style>
