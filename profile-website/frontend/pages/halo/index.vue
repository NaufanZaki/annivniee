<!-- :navigation="true"
:pagination="true" -->
<template>
  <p class="text-lg text-gray-600 mt-20 text-center">ppppppppppp</p>

  <h1 class="text-4xl font-extrabold text-center mt-4">
    ciee udah setaun xixiixixixii
  </h1>
  <swiper
    :cssMode="true"
    :mousewheel="true"
    :keyboard="true"
    :modules="modules"
    class="flex m-20 mx-40"
  >
    <swiper-slide v-for="(budiItem, index) in budi" :key="index">
      <div class="mx-40 flex justify-center">
        <img
          :src="budiItem.image"
          alt="Anniv"
          width="250px"
          height="auto"
        />
      </div>
    </swiper-slide>
  </swiper>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";

import "swiper/css";

import "swiper/css/navigation";
import "swiper/css/pagination";

// import required modules
import { Navigation, Pagination, Mousewheel, Keyboard } from "swiper/modules";

export default {
  data() {
    return {
      activeIndex: 0,
      budi: [
        {
          id: 1,
          image: "/foto/foto1.png",
        },
        {
          id: 2,
          image: "/foto/foto2.jpg",
        },
        {
          id: 3,
          image: "/foto/foto4.jpg",
        },
        {
          id: 4,
          image: "/foto/foto5.jpg",
        },
        {
          id: 5,
          image: "/foto/foto6.jpg",
        },
        {
          id: 6,
          image: "/foto/foto7.jpg",
        },
        // {
        //   id: 7,
        //   image: "/foto/foto3.png",
        // }
      ],
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Navigation, Pagination, Mousewheel, Keyboard],
    };
  },
};
</script>
