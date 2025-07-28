<script>
    import AOS from 'aos';
</script>
<section class=" py-2 px-3" id="contact" >
    <h1 class="text-center text-primary mb-5 display-3 fw-bold d-flex align-items-center justify-content-center">Let's Connect ! <img src="https://www.mejdi.ch/emojis/envelope.png" class="ms-2 mb-2" alt="" data-aos="fade-right"></h1>
    <p class="text-center fw-bold d-flex align-items-center justify-content-center fs-2 w-75 mx-auto mb-5" data-aos="fade-right">Have a question, suggestion, or just want to chat? Shoot me a message using the contact form below, and I’ll get back to you in no time!</p>
        <form action="#" method="POST" class="w-50 mx-auto p-3" data-aos="fade-up">

        <label for="name" class="form-label ms-2">Full Name: </label>
        <input type="text" id="name" class="form-control form-control-lg border rounded-pill p-3 border-primary mb-4" placeholder="Foulen el fouleni" required>

        <label for="email" class="form-label ms-2">Email Adress: </label>
        <input type="EMAIL" id="email" class="form-control form-control-lg border rounded-pill p-3 border-primary mb-4" placeholder="exmple@gmail.com">

        <label for="service" class="form-label ms-2">Service: </label>
        <select name="service" id="service" class="form-select form-select-lg border rounded-pill p-3 border-primary mb-4" required>
            <option value="" class="text-primary">--Select a Service--</option>
            <option value="" class="text-primary">Front-end Web site</option>
            <option value="" class="text-primary">Back-end Web site</option>
            <option value="" class="text-primary">Full Stack Web site</option>
        </select>

        <div class="form-floating msg">
            <textarea name="message" class="form-control form-control-lg border rounded-3 p-3 border-primary mb-4" id="message" cols="50" rows="5" placeholder="message..." required></textarea>
        </div>
        <button class="btn btn-outline-primary mt-4 w-100 rounded-5">Get in touch</button>
    </form>
</section>

<style>
    section{
        height: 90vh;
        margin-top: 15rem;
    }
    input{
        background-color: transparent;
    }
    select{
        background-color: transparent;
        color: white;
    }
    .form-control::placeholder {
    color: white;
  }
  .form-control:focus, .form-select:focus {
    background-color: transparent;
    color: white;
    box-shadow: none;
  }
#message{
    resize: none;
    height: 150px;
    background-color: transparent;
    color: white;
}
#message::placeholder{
    color: white;
}
</style>