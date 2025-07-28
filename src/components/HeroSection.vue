<script>
export default {
      name: 'HeroSection',
      mounted() {
            this.initTyped();
      },
      methods: {
            /**
             * Init typed.js
             */
            initTyped() {
                  const selectTyped = document.querySelector('.typed');
                  if (selectTyped) {
                        let typed_strings = selectTyped.getAttribute('data-typed-items');
                        typed_strings = typed_strings.split(',');
                        new Typed('.typed', {
                              strings: typed_strings,
                              loop: true,
                              typeSpeed: 100,
                              backSpeed: 50,
                              backDelay: 2000
                        });
                  }
            }
      }

};
</script>
<template>
      <section id="hero" class="hero section dark-background">

            <img src="../assets/img/hero-bg.jpg" alt="" data-aos="fade-in" class="">

            <div class="container" data-aos="fade-up" data-aos-delay="100">
                  <h2>Muzaffar Hussain</h2>
                  <p>I'm <span class="typed"
                              data-typed-items="Developer, Freelancer,Project Manager, Software Engineer">Developer</span><span
                              class="typed-cursor typed-cursor--blink" aria-hidden="true"></span><span
                              class="typed-cursor typed-cursor--blink" aria-hidden="true"></span></p>
            </div>

      </section>
</template>