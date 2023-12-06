<template>
<carousel :items="carouselItems"></carousel>
</template>

<script>
import Carousel from './components/Carousel.vue';

export default {
  data() {
    return {
      carouselItems: [
        { src: '../public/hoodie-1.jpeg', alt: 'Hoodie 1', i: 1 },
        { src: '../public/hoodie-2.jpeg', alt: 'Hoodie 2', i: 2 },
        { src: '../public/hoodie-3.jpeg', alt: 'Hoodie 3', i: 3 },
        { src: '../public/hoodie-4.jpeg', alt: 'Hoodie 4', i: 4 },
        { src: '../public/hoodie-5.jpeg', alt: 'Hoodie 5', i: 5 },
        { src: '../public/hoodie-6.jpeg', alt: 'Hoodie 6', i: 6 }
      ]
    };
  },
  components: {
    Carousel
  }
};
</script>
