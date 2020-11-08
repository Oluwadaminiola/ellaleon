<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light fixed-top">
      <div class="container">
        <a class="navbar-brand" href="/">EllaLeon.</a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <i class="fas fa-bars"></i>
        </button>
        
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav ml-auto">
            <li class="nav-item link" :class="{ active: $route.path == '/' }">
              <a class="nav-link" @click="home()">Home</a>
            </li>
            <li class="nav-item dropdown">
              <a
                class="nav-link dropdown-toggle"
                href="#"
                id="navbarDropdown"
                role="button"
                data-toggle="dropdown"
                aria-haspopup="true"
                aria-expanded="false"
                :class="{
                  active: $route.path == '/about' || $route.path == '/hse-policy' || $route.path == '/environmentalpolicy' || $route.path == '/communityaffairs'}"
              >
                Who We Are
              </a>
              <div class="dropdown-menu" aria-labelledby="navbarDropdown">
                <a class="dropdown-item" @click="about()">About Us</a>
                <a class="dropdown-item" @click="hse()">HSE Policy</a>
                <a class="dropdown-item" @click="env()">Environmental Policy</a>
                <a class="dropdown-item" @click="com()">Community Affairs</a>
              </div>
            </li>
            <li class="nav-item dropdown">
              <a
                class="nav-link dropdown-toggle"
                href="#"
                id="navbarDropdown"
                role="button"
                data-toggle="dropdown"
                aria-haspopup="true"
                aria-expanded="false"
                :class="{
                  active:
                    $route.path == '/construction' ||
                    $route.path == '/civilengineering' ||
                    $route.path == '/mechanicalengineering' ||
                    $route.path == '/procurement',
                }"
              >
                Services
              </a>
              <div class="dropdown-menu" aria-labelledby="navbarDropdown">
                <a class="dropdown-item" @click="pro()">Procurement</a>
                <a class="dropdown-item" @click="real()"
                  >Real Estate & Building Construction</a
                >
                <a class="dropdown-item" @click="mech()"
                  >Mechanical Engineering</a
                >
                <a class="dropdown-item" @click="civil()"
                  >Civil Engineering</a
                >
              </div>
            </li>
            <li
              class="nav-item link"
              :class="{ active: $route.path == '/projects' }"
            >
              <a class="nav-link" @click="projects()">Projects</a>
            </li>
            <li
              class="nav-item link"
              :class="{ active: $route.path == '/contactus' }"
            >
              <a class="nav-link" @click="contact()">Contact Us</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- <nav class="navbar navbar-expand-lg">
      <div class="container">
        <a class="navbar-brand" href="/">EllaLeon.</a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <i class="fas fa-bars"></i>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav ml-auto">
            <li class="nav-item link" :class="{ active: $route.path == '/' }">
              <a class="nav-link" href="/">Home</a>
            </li>

            <li
              class="nav-item dropdown mx-3"
              :class="{
                active: $route.path == '/about' || $route.path == '/hse-policy',
              }"
            >
              <a
                class="dropdown-toggle nav-link"
                data-toggle="dropdown"
                role="button"
              >
                <span class=" "> Who We Are </span>
              </a>
              <ul class="dropdown-menu">
                <li>
                  <a class="dropdown-item mb-2" href="/about">About Us</a>
                </li>
                <li>
                  <a class="dropdown-item mb-2" href="/hse-policy"
                    >HSE Policy</a
                  >
                </li>
              </ul>
            </li>
            <li
              class="nav-item link dropdown mx-3"
              :class="{
                active:
                  $route.path == '/construction' ||
                  $route.path == '/civilengineering' ||
                  $route.path == '/mechanicalengineering' ||
                  $route.path == '/procurement',
              }"
            >
              <a
                class="dropdown-toggle nav-link"
                data-toggle="dropdown"
                role="button"
              >
                <span class=""> Services </span>
              </a>
              <ul class="dropdown-menu">
                <li>
                  <a class="dropdown-item mb-2" href="/procurement"
                    >Procurement</a
                  >
                </li>
                <li>
                  <a class="dropdown-item mb-2" href="/construction"
                    >Real Estate & Building Construction</a
                  >
                </li>
                <li>
                  <a class="dropdown-item mb-2" href="/mechanicalengineering"
                    >Mechanical Engineering</a
                  >
                </li>
                <li>
                  <a class="dropdown-item mb-2" href="/civilengineering"
                    >Civil Engineering</a
                  >
                </li>
              </ul>
            </li>
            <li class="nav-item link">
              <a class="nav-link" href="/projects">Projects</a>
            </li>
            <li class="nav-item link">
              <a class="nav-link" href="/contactus">Contact Us</a>
            </li>
          </ul>
        </div>
      </div>
    </nav> -->

    <!-- <div class="phone">
      <div class="content">
        <nav role="navigation">
          <div id="menuToggle">
            <input type="checkbox" />
            <span></span>
            <span></span>
            <span></span>
            <ul id="menu">
              <li><a href="#">Home</a></li>
              <li><a href="#">About</a></li>
              <li><a href="#">Info</a></li>
              <li><a href="#">Contact</a></li>
            </ul>
          </div>
        </nav>
      </div>
    </div> -->
  </div>
</template>
<script>
export default {
  mounted() {
    $(window).scroll(function () {
      if ($(document).scrollTop() > 100) {
        $("nav.navbar").addClass("navchange");
      } else {
        $("nav.navbar").removeClass("navchange");
      }
    });
  },
  methods: {
    home(){
       this.$router.push({ path: "/" });
    },
    about(){
       this.$router.push({ path: "/about" });
    },
    hse(){
       this.$router.push({ path: "/hse-policy" });
    },
    env(){
       this.$router.push({ path: "/environmentalpolicy" });
    },
    com(){
       this.$router.push({ path: "/communityaffairs" });
    },
    pro(){
       this.$router.push({ path: "/procurement" });
    },
    real(){
       this.$router.push({ path: "/construction" });
    },
    mech(){
       this.$router.push({ path: "/mechanicalengineering" });
    },
    civil(){
       this.$router.push({ path: "/civilengineering" });
    },
    projects(){
       this.$router.push({ path: "/projects" });
    },
    contact(){
       this.$router.push({ path: "/contactus" });
    }
  }
};
</script>

<style scoped>
#menuToggle {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 25px;
  right: 25px;
  z-index: 1;
  -webkit-user-select: none;
  user-select: none;
}

#menuToggle input {
  display: flex;
  width: 40px;
  height: 32px;
  position: absolute;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}

#menuToggle span {
  display: flex;
  width: 29px;
  height: 2px;
  margin-bottom: 5px;
  position: relative;
  background: #ffffff;
  border-radius: 3px;
  z-index: 1;
  transform-origin: 5px 0px;
  transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1),
    background 0.5s cubic-bezier(0.77, 0.2, 0.05, 1), opacity 0.55s ease;
}

#menuToggle span:first-child {
  transform-origin: 0% 0%;
}

#menuToggle span:nth-last-child(2) {
  transform-origin: 0% 100%;
}

#menuToggle input:checked ~ span {
  opacity: 1;
  transform: rotate(45deg) translate(-3px, -1px);
  background: #36383f;
}
#menuToggle input:checked ~ span:nth-last-child(3) {
  opacity: 0;
  transform: rotate(0deg) scale(0.2, 0.2);
}

#menuToggle input:checked ~ span:nth-last-child(2) {
  transform: rotate(-45deg) translate(0, -1px);
}

#menu {
  position: fixed;
  /* z-index: 10; */
  width: 50vw !important;
  height: 102vh;
  box-shadow: 0 0 10px #85888c;
  margin: 0 -50px -50px 0;
  /* margin: -50px 0 0 -50px; */
  padding: 50px;
  padding-top: 125px;
  background-color: #f5f6fa;
  -webkit-font-smoothing: antialiased;
  transform-origin: 0% 0%;
  transform: translate(-100%, 0);
  transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1);
}

#menu li {
  padding: 10px 0;
  transition-delay: 2s;
}

#menuToggle input:checked ~ ul {
  transform: none;
}
</style>