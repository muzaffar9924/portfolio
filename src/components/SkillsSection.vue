<script>
export default {
    name: 'SkillSections',
    mounted() {
        this.skillsAnimation();
        this.glightboxl();

    },
    methods: {
        /**
        * Animate the skills items on reveal
        */
        skillsAnimation() {
            let skillsAnimation = document.querySelectorAll('.skills-animation');
            console.log(skillsAnimation)
            skillsAnimation.forEach((item) => {
                console.log(item)
                new Waypoint({
                    element: item,
                    offset: '80%',
                    handler: function (direction) {
                        let progress = item.querySelectorAll('.progress .progress-bar');
                        progress.forEach(el => {
                            el.style.width = el.getAttribute('aria-valuenow') + '%';
                        });
                    }
                });
            });
        },
        glightboxl() {
            GLightbox({
                selector: '.glightbox'
            });
        }

    }

};
</script>
<template>
    <section id="skills" class="skills section light-background">
        <!-- Section Title -->
        <div class="container section-title" data-aos="fade-up">
            <h2>Skills</h2>
            <p>Necessitatibus eius consequatur ex aliquid fuga eum quidem sint consectetur velit</p>
        </div><!-- End Section Title -->
        <div class="container" data-aos="fade-up" data-aos-delay="100">
            <div class="row skills-content skills-animation">
                <div class="col-lg-3">
                    <div class="progress">
                        <span class="skill"><span>HTML /CSS /Bootstrap</span> <i class="val">80%</i></span>
                        <div class="progress-bar-wrap">
                            <div class="progress-bar w-80" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                    </div><!-- End Skills Item -->
                    <div class="progress">
                        <span class="skill"><span>React JS/Vue JS/Blade</span> <i class="val">90%</i></span>
                        <div class="progress-bar-wrap">
                            <div class="progress-bar w-90" aria-valuenow="90" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                    </div><!-- End Skills Item -->
                    <div class="progress">
                        <span class="skill"><span>JavaScript/JQuery/AJAX</span> <i class="val">75%</i></span>
                        <div class="progress-bar-wrap">
                            <div class="progress-bar w-75" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                    </div><!-- End Skills Item -->
                </div>
                <div class="col-lg-3">
                    <div class="progress">
                        <span class="skill"><span>PHP</span> <i class="val">80%</i></span>
                        <div class="progress-bar-wrap">
                            <div class="progress-bar w-80" aria-valuenow="80" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                    </div><!-- End Skills Item -->
                    <div class="progress">
                        <span class="skill"><span>WordPress/CMS</span> <i class="val">80%</i></span>
                        <div class="progress-bar-wrap">
                            <div class="progress-bar w-80" aria-valuenow="90" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                    </div><!-- End Skills Item -->
                    <div class="progress">
                        <span class="skill"><span>Laravel/CodeIgniter</span> <i class="val">99%</i></span>
                        <div class="progress-bar-wrap">
                            <div class="progress-bar w-99" style="width: 80%;" aria-valuenow="55" aria-valuemin="0"
                                aria-valuemax="100">
                            </div>
                        </div>
                    </div><!-- End Skills Item -->
                </div>
                <div class="col-lg-3">
                    <div class="progress">
                        <span class="skill"><span>Node JS/Express JS/Next JS</span> <i class="val">80%</i></span>
                        <div class="progress-bar-wrap">
                            <div class="progress-bar w-80" aria-valuenow="80" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                    </div><!-- End Skills Item -->
                    <div class="progress">
                        <span class="skill"><span>JWT</span> <i class="val">90%</i></span>
                        <div class="progress-bar-wrap">
                            <div class="progress-bar w-90" aria-valuenow="90" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                    </div><!-- End Skills Item -->
                    <div class="progress">
                        <span class="skill"><span>REST / SOAP APIs</span> <i class="val">100%</i></span>
                        <div class="progress-bar-wrap">
                            <div class="progress-bar w-100" aria-valuenow="55" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                    </div><!-- End Skills Item -->
                </div>
                <div class="col-lg-3">
                    <div class="progress">
                        <span class="skill"><span>AWS</span> <i class="val">50%</i></span>
                        <div class="progress-bar-wrap">
                            <div class="progress-bar w-50" aria-valuenow="80" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                    </div><!-- End Skills Item -->
                </div>
            </div>
        </div>
    </section>
</template>