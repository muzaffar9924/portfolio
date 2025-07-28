<script setup>
import Header from './components/SideMenu.vue';
import HeroSection from './components/HeroSection.vue';
import AboutSection from './components/AboutSection.vue';
import StatsSection from './components/StatsSection.vue';
import SkillsSection from './components/SkillsSection.vue';
import ResumeSection from './components/ResumeSection.vue';
import PortfolioSection from './components/PortfolioSection.vue';
import TestimonialsSection from './components/TestimonialsSection.vue';
import ContactSection from './components/ContactSection.vue';
import ServicesSection from './components/ServicesSection.vue';



// FOR MAIN JS

(function () {
    "use strict";

    /**
     * Toggle mobile nav dropdowns
     */
    document.querySelectorAll('.navmenu .toggle-dropdown').forEach(navmenu => {
        navmenu.addEventListener('click', function (e) {
            e.preventDefault();
            this.parentNode.classList.toggle('active');
            this.parentNode.nextElementSibling.classList.toggle('dropdown-active');
            e.stopImmediatePropagation();
        });
    });

    /**
     * Preloader
     */
    const preloader = document.querySelector('#preloader');
    if (preloader) {
        window.addEventListener('load', () => {
            preloader.remove();
        });
    }

    /**
     * Scroll top button
     */
    // let scrollTop = document.querySelector('.scroll-top');

    // function toggleScrollTop() {
    //     if (scrollTop) {
    //         window.scrollY > 100 ? scrollTop.classList.add('active') : scrollTop.classList.remove('active');
    //     }
    // }
    // scrollTop.addEventListener('click', (e) => {
    //     e.preventDefault();
    //     window.scrollTo({
    //         top: 0,
    //         behavior: 'smooth'
    //     });
    // });

    // window.addEventListener('load', toggleScrollTop);
    // document.addEventListener('scroll', toggleScrollTop);

    /**
     * Animation on scroll function and init
     */
    function aosInit() {
        AOS.init({
            duration: 600,
            easing: 'ease-in-out',
            once: true,
            mirror: false
        });
    }
    window.addEventListener('load', aosInit);



    /**
     * Init isotope layout and filters
     */
    document.querySelectorAll('.isotope-layout').forEach(function (isotopeItem) {
        let layout = isotopeItem.getAttribute('data-layout') ?? 'masonry';
        let filter = isotopeItem.getAttribute('data-default-filter') ?? '*';
        let sort = isotopeItem.getAttribute('data-sort') ?? 'original-order';

        let initIsotope;
        imagesLoaded(isotopeItem.querySelector('.isotope-container'), function () {
            initIsotope = new Isotope(isotopeItem.querySelector('.isotope-container'), {
                itemSelector: '.isotope-item',
                layoutMode: layout,
                filter: filter,
                sortBy: sort
            });
        });

        isotopeItem.querySelectorAll('.isotope-filters li').forEach(function (filters) {
            filters.addEventListener('click', function () {
                isotopeItem.querySelector('.isotope-filters .filter-active').classList.remove('filter-active');
                this.classList.add('filter-active');
                initIsotope.arrange({
                    filter: this.getAttribute('data-filter')
                });
                if (typeof aosInit === 'function') {
                    aosInit();
                }
            }, false);
        });

    });

    /**
     * Init swiper sliders
     */
    function initSwiper() {
        document.querySelectorAll(".init-swiper").forEach(function (swiperElement) {
            let config = JSON.parse(
                swiperElement.querySelector(".swiper-config").innerHTML.trim()
            );

            if (swiperElement.classList.contains("swiper-tab")) {
                initSwiperWithCustomPagination(swiperElement, config);
            } else {
                new Swiper(swiperElement, config);
            }
        });
    }

    window.addEventListener("load", initSwiper);

    /**
     * Correct scrolling position upon page load for URLs containing hash links.
     */
    window.addEventListener('load', function (e) {
        if (window.location.hash) {
            if (document.querySelector(window.location.hash)) {
                setTimeout(() => {
                    let section = document.querySelector(window.location.hash);
                    let scrollMarginTop = getComputedStyle(section).scrollMarginTop;
                    window.scrollTo({
                        top: section.offsetTop - parseInt(scrollMarginTop),
                        behavior: 'smooth'
                    });
                }, 100);
            }
        }
    });

    /**
     * Navmenu Scrollspy
     */
    let navmenulinks = document.querySelectorAll('.navmenu a');

    function navmenuScrollspy() {
        navmenulinks.forEach(navmenulink => {
            if (!navmenulink.hash) return;
            let section = document.querySelector(navmenulink.hash);
            if (!section) return;
            let position = window.scrollY + 200;
            if (position >= section.offsetTop && position <= (section.offsetTop + section.offsetHeight)) {
                document.querySelectorAll('.navmenu a.active').forEach(link => link.classList.remove('active'));
                navmenulink.classList.add('active');
            } else {
                navmenulink.classList.remove('active');
            }
        })
    }
    window.addEventListener('load', navmenuScrollspy);
    document.addEventListener('scroll', navmenuScrollspy);

})();

</script>

<template>
    <!-- Main Hearder -->
    <Header />
    <!-- /Main Hearder -->
    <main class="main">
        <!-- Hero Section -->
        <HeroSection />
        <!-- /Hero Section -->
        <!-- About Section -->
        <AboutSection />
        <!-- /About Section -->

        <!-- Stats Section -->
        <StatsSection />
        <!-- /Stats Section -->

        <!-- Skills Section -->
        <SkillsSection />
        <!-- /Skills Section -->

        <!-- Resume Section -->
        <ResumeSection />
        <!-- /Resume Section -->

        <!-- Portfolio Section -->
        <!-- <PortfolioSection /> -->
        <!-- /Portfolio Section -->

        <!-- Services Section -->
        <!-- <ServicesSection /> -->
        <!-- /Services Section -->

        <!-- Testimonials Section -->
        <!-- <TestimonialsSection /> -->
        <!-- /Testimonials Section -->

        <!-- Contact Section -->
        <!-- <ContactSection /> -->
        <!-- /Contact Section-->
    </main>
    <!-- Scroll Top -->
    <a href="#" id="scroll-top" class="scroll-top d-flex align-items-center justify-content-center"><i
            class="bi bi-arrow-up-short"></i></a>

    <!-- Preloader   -->
    <!-- <div id="preloader"></div> -->
</template>
