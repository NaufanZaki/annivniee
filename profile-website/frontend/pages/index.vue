<template>
  <div class="container mx-auto p-8">
    <!-- Header image -->
    <div id="header-carousel" class="carousel">
      <div class="carousel-inner">
        <div v-for="(image, index) in headerImages" :key="index" class="carousel-item" :class="{ active: index === activeIndex }">
          <img
            :src="image"
            :alt="'Anniversary Image ' + (index + 1)"
            class="mx-auto h-60 w-48 object-cover mb-4 rounded-lg shadow-lg"
          />
        </div>
      </div>
      <a class="carousel-control-prev" href="#" role="button" @click="prevSlide">
        <span aria-hidden="true">&lt;</span>
      </a>
      <a class="carousel-control-next" href="#" role="button" @click="nextSlide">
        <span aria-hidden="true">&gt;</span>
      </a>
    </div>

    <!-- Header Text -->
    <h1 class="text-4xl font-extrabold text-center mt-4">ciee udah setaun xixiixixixii</h1>

    <!-- Content -->
    <p class="text-lg text-gray-600 mt-4">
      ppppppppppp
    </p>


  </div>
</template>

<script>
export default {
  data() {
    return {
      headerImages: ["/assets/foto/foto1.png", "/assets/foto/foto2.jpg", "/assets/foto/foto3.png", "/assets/foto/foto4.jpg"],
      activeIndex: 0,
    };
  },
  methods: {
    nextSlide() {
      this.activeIndex = (this.activeIndex + 1) % this.headerImages.length;
    },
    prevSlide() {
      this.activeIndex = (this.activeIndex - 1 + this.headerImages.length) % this.headerImages.length;
    },
  },
};
</script>

<style scoped>
/* Add your custom styles here using Tailwind CSS classes */

/* Carousel Styles */
.carousel {
  position: relative;
  overflow: hidden;
  margin-top: 2rem;
}

.carousel-inner {
  display: flex;
  transition: transform 0.5s ease-in-out;
}

.carousel-item {
  flex: 0 0 100%;
}

.carousel-control-prev,
.carousel-control-next {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  font-size: 2rem;
  cursor: pointer;
  color: #fff;
}

.carousel-control-prev {
  left: 0.5rem;
}

.carousel-control-next {
  right: 0.5rem;
}

/* Active carousel item */
.carousel-item.active {
  opacity: 1;
}
</style>
