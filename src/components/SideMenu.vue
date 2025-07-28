<script>
export default {
      name: 'SideMenu',
      mounted() {
            this.setupHeaderToggle(); 
      },
      methods: {
            setupHeaderToggle() {
                  // Ensure elements exist before attaching event listeners
                  const headerToggleBtn = document.querySelector('.header-toggle');
                  const header = document.querySelector('#header');
                  const navmenuLinks = document.querySelectorAll('#navmenu a');

                  // Check if elements exist before attaching event listeners
                  if (headerToggleBtn && header) {
                        headerToggleBtn.addEventListener('click', this.headerToggle);
                  }

                  navmenuLinks.forEach(navmenu => {
                        navmenu.addEventListener('click', this.hideMobileNav);
                  });
            },
            headerToggle() {
                  const header = document.querySelector('#header');
                  const headerToggleBtn = document.querySelector('.header-toggle');
                  header.classList.toggle('header-show');
                  headerToggleBtn.classList.toggle('bi-list');
                  headerToggleBtn.classList.toggle('bi-x');
            },
            hideMobileNav() {
                  const header = document.querySelector('#header');
                  const headerToggleBtn = document.querySelector('.header-toggle');
                  if (header.classList.contains('header-show')) {
                        this.headerToggle();
                  }
            }
      }
};
</script>
<template>
      <header id="header" class="header dark-background d-flex flex-column">
            <i class="header-toggle d-xl-none bi bi-list"></i>

            <div class="profile-img">
                  <img src="../assets/img/profile.jpg" alt="" class="img-fluid rounded-circle">
            </div>

            <a href="index.html" class="logo d-flex align-items-center justify-content-center">
                  <h1 class="sitename">Muzaffar Hussain</h1>
            </a>

            <div class="social-links text-center">
                  <a href="#" class="twitter" title="Twitter"><i class="bi bi-twitter-x"></i></a>
                  <a href="#" class="facebook" title="Facebook"><i class="bi bi-facebook"></i></a>
                  <a href="#" class="instagram" title="Instagram"><i class="bi bi-instagram"></i></a>
                  <a href="#" class="google-plus" title="Microsoft Teams"><i class="bi bi-microsoft-teams"></i></a>
                  <a href="#" class="linkedin" title="Linkedin"><i class="bi bi-linkedin"></i></a>
            </div>

            <nav id="navmenu" class="navmenu">
                  <ul>
                        <li><a href="#hero" class="active"><i class="bi bi-house navicon"></i>Home</a></li>
                        <li><a href="#about"><i class="bi bi-person navicon"></i> About</a></li>
                        <li><a href="#resume"><i class="bi bi-file-earmark-text navicon"></i> Resume</a></li>
                        <!-- <li><a href="#portfolio"><i class="bi bi-images navicon"></i> Portfolio</a></li>
                        <li><a href="#services"><i class="bi bi-hdd-stack navicon"></i> Services</a></li>
                        <li class="dropdown"><a href="#"><i class="bi bi-menu-button navicon"></i> <span>Dropdown</span>
                                    <i class="bi bi-chevron-down toggle-dropdown"></i></a>
                              <ul>
                                    <li><a href="#">Dropdown 1</a></li>
                                    <li class="dropdown"><a href="#"><span>Deep Dropdown</span> <i
                                                      class="bi bi-chevron-down toggle-dropdown"></i></a>
                                          <ul>
                                                <li><a href="#">Deep Dropdown 1</a></li>
                                                <li><a href="#">Deep Dropdown 2</a></li>
                                                <li><a href="#">Deep Dropdown 3</a></li>
                                                <li><a href="#">Deep Dropdown 4</a></li>
                                                <li><a href="#">Deep Dropdown 5</a></li>
                                          </ul>
                                    </li>
                                    <li><a href="#">Dropdown 2</a></li>
                                    <li><a href="#">Dropdown 3</a></li>
                                    <li><a href="#">Dropdown 4</a></li>
                              </ul>
                        </li>
                        <li><a href="#contact"><i class="bi bi-envelope navicon"></i> Contact</a></li> -->
                  </ul>
            </nav>
      </header>
</template>