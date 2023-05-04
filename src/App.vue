<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import VideoBackground from './components/VideoBackground.vue'
</script>

<template>
 <VideoBackground />   
 
<header class="header">
  <button class="navbar-toggler" type="button" @click="toggleSlideMenu">
      <span class="navbar-toggler-icon">
        <svg class="toggle-icon" xmlns="http://www.w3.org/2000/svg"  viewBox="0 0 50 50" width="150px" height="150px"><path d="M 0 7.5 L 0 12.5 L 50 12.5 L 50 7.5 Z M 0 22.5 L 0 27.5 L 50 27.5 L 50 22.5 Z M 0 37.5 L 0 42.5 L 50 42.5 L 50 37.5 Z"/></svg>
      </span>
    </button>
    <div class="header-left">
        <img class="header-image" src="./images/logo.png"/>
        <div class="header-icon-est">Est. 2003</div>
    </div>
    
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
  <div class="container-fluid">
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav ms-auto" v-if="!showSlideMenu">
        <li class="nav-item">
          <router-link  class="nav-link active" aria-current="page" to="/">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/about">About</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/music">Music</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/tour">Tour Dates</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/merch">Merchandise</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/contact">Contact</router-link>
        </li>
      </ul>
      <ul class="slide-menu" :class="{ open: showSlideMenu }" >
        <li class="nav-item">
          <router-link @click="toggleSlideMenu" class="nav-link active" aria-current="page" to="/">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link @click="toggleSlideMenu" class="nav-link" to="/about">About</router-link>
        </li>
        <li class="nav-item">
          <router-link @click="toggleSlideMenu" class="nav-link" to="/music">Music</router-link>
        </li>
        <li class="nav-item">
          <router-link @click="toggleSlideMenu" class="nav-link" to="/tour">Tour Dates</router-link>
        </li>
        <li class="nav-item">
          <router-link @click="toggleSlideMenu" class="nav-link" to="/merch">Merchandise</router-link>
        </li>
        <li class="nav-item">
          <router-link @click="toggleSlideMenu" class="nav-link" to="/contact">Contact</router-link>
        </li>
      </ul>
    </div>
  </div>
</nav>
</header>
<router-view></router-view>
<!-- SOCIALS -->
<footer class="container">
    <div class="social-follow">Follow us on social:</div>
    
    <div class="socials-icons">
        <a href="https://www.instagram.com/cdpred/?hl=en" >
        <svg  xmlns="http://www.w3.org/2000/svg" width="30px" height="30px" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z" ></path></svg>
        </a>

        <a href="https://open.spotify.com/artist/5Lv9Qc7dCi7vps4rQ5MfTV" >
        <svg  xmlns="http://www.w3.org/2000/svg" width="30px" height="30px" version="1.1" viewBox="0 0 168 168">
        <path d="m83.996 0.277c-46.249 0-83.743 37.493-83.743 83.742 0 46.251 37.494 83.741 83.743 83.741 46.254 0 83.744-37.49 83.744-83.741 0-46.246-37.49-83.738-83.745-83.738l0.001-0.004zm38.404 120.78c-1.5 2.46-4.72 3.24-7.18 1.73-19.662-12.01-44.414-14.73-73.564-8.07-2.809 0.64-5.609-1.12-6.249-3.93-0.643-2.81 1.11-5.61 3.926-6.25 31.9-7.291 59.263-4.15 81.337 9.34 2.46 1.51 3.24 4.72 1.73 7.18zm10.25-22.805c-1.89 3.075-5.91 4.045-8.98 2.155-22.51-13.839-56.823-17.846-83.448-9.764-3.453 1.043-7.1-0.903-8.148-4.35-1.04-3.453 0.907-7.093 4.354-8.143 30.413-9.228 68.222-4.758 94.072 11.127 3.07 1.89 4.04 5.91 2.15 8.976v-0.001zm0.88-23.744c-26.99-16.031-71.52-17.505-97.289-9.684-4.138 1.255-8.514-1.081-9.768-5.219-1.254-4.14 1.08-8.513 5.221-9.771 29.581-8.98 78.756-7.245 109.83 11.202 3.73 2.209 4.95 7.016 2.74 10.733-2.2 3.722-7.02 4.949-10.73 2.739z" ></path>
        </svg>
        </a>

        <a href="https://www.youtube.com/channel/UCbu61gfevn5crDayYZnMSwg" >
        <svg  width="30px" height="30px" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 461.001 461.001" xml:space="preserve"><g >
            <path d="M365.257,67.393H95.744C42.866,67.393,0,110.259,0,163.137v134.728
            c0,52.878,42.866,95.744,95.744,95.744h269.513c52.878,0,95.744-42.866,95.744-95.744V163.137
            C461.001,110.259,418.135,67.393,365.257,67.393z M300.506,237.056l-126.06,60.123c-3.359,1.602-7.239-0.847-7.239-4.568V168.607
            c0-3.774,3.982-6.22,7.348-4.514l126.06,63.881C304.363,229.873,304.298,235.248,300.506,237.056z" ></path></g>
        </svg>
        </a>

        <a href="https://twitter.com/CDPROJEKTRED" >
        <svg  height="30px" width="30px" version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 410.155 410.155" xml:space="preserve">
            <path d="M403.632,74.18c-9.113,4.041-18.573,7.229-28.28,9.537c10.696-10.164,18.738-22.877,23.275-37.067
                l0,0c1.295-4.051-3.105-7.554-6.763-5.385l0,0c-13.504,8.01-28.05,14.019-43.235,17.862c-0.881,0.223-1.79,0.336-2.702,0.336
                c-2.766,0-5.455-1.027-7.57-2.891c-16.156-14.239-36.935-22.081-58.508-22.081c-9.335,0-18.76,1.455-28.014,4.325
                c-28.672,8.893-50.795,32.544-57.736,61.724c-2.604,10.945-3.309,21.9-2.097,32.56c0.139,1.225-0.44,2.08-0.797,2.481
                c-0.627,0.703-1.516,1.106-2.439,1.106c-0.103,0-0.209-0.005-0.314-0.015c-62.762-5.831-119.358-36.068-159.363-85.14l0,0
                c-2.04-2.503-5.952-2.196-7.578,0.593l0,0C13.677,65.565,9.537,80.937,9.537,96.579c0,23.972,9.631,46.563,26.36,63.032
                c-7.035-1.668-13.844-4.295-20.169-7.808l0,0c-3.06-1.7-6.825,0.485-6.868,3.985l0,0c-0.438,35.612,20.412,67.3,51.646,81.569
                c-0.629,0.015-1.258,0.022-1.888,0.022c-4.951,0-9.964-0.478-14.898-1.421l0,0c-3.446-0.658-6.341,2.611-5.271,5.952l0,0
                c10.138,31.651,37.39,54.981,70.002,60.278c-27.066,18.169-58.585,27.753-91.39,27.753l-10.227-0.006
                c-3.151,0-5.816,2.054-6.619,5.106c-0.791,3.006,0.666,6.177,3.353,7.74c36.966,21.513,79.131,32.883,121.955,32.883
                c37.485,0,72.549-7.439,104.219-22.109c29.033-13.449,54.689-32.674,76.255-57.141c20.09-22.792,35.8-49.103,46.692-78.201
                c10.383-27.737,15.871-57.333,15.871-85.589v-1.346c-0.001-4.537,2.051-8.806,5.631-11.712c13.585-11.03,25.415-24.014,35.16-38.591
                l0,0C411.924,77.126,407.866,72.302,403.632,74.18L403.632,74.18z" ></path>
        </svg>
        </a>

        <a href="https://www.facebook.com/CDPROJEKTRED/" >
        <svg  height="30px" width="30px" version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 408.788 408.788" xml:space="preserve">
            <path d="M353.701,0H55.087C24.665,0,0.002,24.662,0.002,55.085v298.616c0,30.423,24.662,55.085,55.085,55.085
                h147.275l0.251-146.078h-37.951c-4.932,0-8.935-3.988-8.954-8.92l-0.182-47.087c-0.019-4.959,3.996-8.989,8.955-8.989h37.882
                v-45.498c0-52.8,32.247-81.55,79.348-81.55h38.65c4.945,0,8.955,4.009,8.955,8.955v39.704c0,4.944-4.007,8.952-8.95,8.955
                l-23.719,0.011c-25.615,0-30.575,12.172-30.575,30.035v39.389h56.285c5.363,0,9.524,4.683,8.892,10.009l-5.581,47.087
                c-0.534,4.506-4.355,7.901-8.892,7.901h-50.453l-0.251,146.078h87.631c30.422,0,55.084-24.662,55.084-55.084V55.085
                C408.786,24.662,384.124,0,353.701,0z" ></path>
        </svg>
        </a>
    </div>
</footer>
</template>

<script>
export default {
  data() {
    return {
      showSlideMenu: false,
    };
  },
  methods: {
    toggleSlideMenu() {
      this.showSlideMenu = !this.showSlideMenu;
    },
    hideSlideMenu() {
      if (window.innerWidth > 1200) {
        this.showSlideMenu = false;
      }
    },
  },
  computed: {
    showButton() {
      return window.innerWidth < 1200;
    },
  },
  mounted() {
    window.addEventListener('resize', this.hideSlideMenu);
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.hideSlideMenu);
  },
};
</script>

<style scoped>
.slide-menu{
  display: none;
}
.navbar-toggler{
  display: none;
}
.navbar {
    width: 100%;
}
 .navbar-nav{
    display: flex;
    list-style-type: none;
 }
 li > a{
    text-decoration: none;
  transition-duration: 500ms;
  color: rgb(244, 230, 10);
  font-size: 2.25rem;
  line-height: 2.5rem;
  margin-right: 2rem;
 }
 li > a:hover,
 li > a:focus{
    color: rgb(244, 230, 10);
  letter-spacing: 0.5rem;
  transition-duration: 500ms;
  border: 1px solid #ffef00;
  border-radius: 10px 10px 10px 10px;
  box-shadow: 0px 0px 5px rgba(255,239,0,0.75);
  padding-left: 5px;
 }
 @media (max-width: 1200px) {
  .header-left{
    display: none;
  }
  .slide-menu.open li:nth-child(3) {
  transition-delay: 0.3s;
}
  .toggle-icon{
    width: 40px;
    height: 40px;
    fill: rgb(244, 230, 10);
  }

  .navbar-nav {
    display: none;
  }

  .navbar-toggler{
    height: 50px;
    display: block;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #1d0025;
  border: 1px solid #4f4252;
  color: #fff;
  font-size: 16px;
  padding: 5px 0 5px 10px;
  text-align: left;
  z-index: 9999;
}
  .slide-menu {
    display: block;
    top: 50px;
    left: -100%;
    width: 100%;
    background-color: #1d0025;
    border: 1px solid #4f4252;
    padding: 10px 0 0 0;
    margin: 0;
    list-style: none;
    position: fixed;
   z-index: 4;
  transition:  0.5s ;
  }
  .slide-menu.open {
  left: 0;
  transition:  0.5s;
}
  .slide-menu li {
    display: block;
    padding: 10px;
    border-bottom: 1px solid #ddd;
  }
  .slide-menu li {
  opacity: 0;
  transform: translateX(-20px);
  transition: opacity 0.5s ease-out, transform 0.5s ease-out;
  transition-delay: 0s;
}

.slide-menu.open li {
  opacity: 1;
  transform: translateX(0);
  transition-delay: 0.1s;
}

.slide-menu.open li:nth-child(2) {
  transition-delay: 0.2s;
}

.slide-menu.open li:nth-child(3) {
  transition-delay: 0.3s;
}
.slide-menu.open li:nth-child(4) {
  transition-delay: 0.4s;
}
.slide-menu.open li:nth-child(5) {
  transition-delay: 0.5s;
}
.slide-menu.open li:nth-child(6) {
  transition-delay: 0.6s;
}
}
</style>
