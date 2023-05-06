<script setup>
//import 'bootstrap/dist/css/bootstrap.css'

import 'bootstrap/dist/js/bootstrap.bundle.js';
</script>

<template>
 <div>
    <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
      <ol class="carousel-indicators">
        <li v-for="(item, index) in images" data-bs-target="#carouselExampleIndicators" :data-bs-slide-to="index" :class="{active: index === 0}"></li>
      </ol>
      <div class="carousel-inner">
        <div v-for="(item, index) in images" :key="index" :class="{active: index === 0}" class="carousel-item">
          <img :src="item.src" class="d-block w-100" alt="...">
        </div>
      </div>
      <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </a>
      <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TheWelcome',
  data() {
    return {
      images: [
        {
          src: 'https://images.pling.com/img/00/00/62/69/92/1682422/samurai-cyberpunk-20771.jpg',
          alt: 'Slide 1',
          title: 'Slide 1 Title',
          description: 'Slide 1 Description',
        },
        {
          src: 'https://i.ytimg.com/vi/VOXOdflScCY/maxresdefault.jpg',
          alt: 'Slide 2',
          title: 'Slide 2 Title',
          description: 'Slide 2 Description',
        },
        {
          src: 'https://i.ytimg.com/vi/-YD6yP5jqMI/maxresdefault.jpg',
          alt: 'Slide 3',
          title: 'Slide 3 Title',
          description: 'Slide 3 Description',
        },
        {
          src: 'https://i.ytimg.com/vi/Igq3d6XA75Y/maxresdefault.jpg',
          alt: 'Slide 3',
          title: 'Slide 3 Title',
          description: 'Slide 3 Description',
        },
      ],
    };
  },
};
</script>

<style scoped>
@import 'bootstrap/dist/css/bootstrap.css';
#carouselExampleIndicators {
  width: 1200px;
  margin-left: auto;
  margin-right: auto;
}
.carousel-item {
  opacity: 0.95;
}
@media (max-width: 1200px) {
  .carousel {
    display: none;
  }
  }
</style>