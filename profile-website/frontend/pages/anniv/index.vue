<template>
  <div class="w-full bg-[#252429]">
    <div id="konten">
      <div class="foto">
        <div class="image">
            <p class="text-[56px] cursor-pointer" @click="klikfoto">
                🤍
            </p>
        </div>
        <span style="font-weight: 700; font-size: 16px" id="sp1">
          
        </span>
        <div id="sp2" style="display: none">
          <span style="font-weight: 700; font-size: 16px" id="finish"></span>
        </div>
      </div>

      <br>
      <br>
      <section>
          <swiper
            :cssMode="true"
            :mousewheel="true"
            :keyboard="true"
            :modules="modules"
            class="flex mx-40 mt-96"
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
            <swiper-slide>
                <div class="flex justify-center">
                    <p class="text-white text-[32px]">klik love di atas dong 💕</p>
                </div>
            </swiper-slide>
          </swiper>
      </section>
    </div>

    <!-- Tombol WhatsApp -->
    <div id="buttonWa" class="cursor-pointer">
      <a class="button whatsapp" @click="bukaWa">
        <i class="icon whatsapp"></i>
        Kirim
      </a>
    </div>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";

import "swiper/css";

import "swiper/css/navigation";
import "swiper/css/pagination";

import { Pagination, Mousewheel, Keyboard } from "swiper/modules";

import Swal from "sweetalert2";
const swals = Swal.mixin({
  cancelButtonColor: "#909090",
  confirmButtonColor: "#00B487",
  allowOutsideClick: false,
});

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
      finish: "kata-kata anniversary tulis sendiri yaak wkwk",
      a: 0,
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Pagination, Mousewheel, Keyboard],
    };
  },
  mounted() {
    this.mulai();
  },
  methods: {
    async mulai() {
      await swals.fire({
        title: `bebas kata-kata `,
        confirmButtonText: "iyaaa",
        showCancelButton: false,
      });
      await swals.fire({
        title: `bebas (klo kebanyakan hapus aja) `,
        confirmButtonText: "lanjut kack",
        showCancelButton: false,
      });
      let zakk = "Zakii";
      let ara = "Mutiara";
      if (zakk) {
        window.zakk = zakk;
        this.finish = this.finish;
        if (ara != zakk) {
          document.getElementById("sp1").innerHTML =
            "PPPP Dari " + zakk + ", buat " + ara + "💕";
          window.ara = ara;
          await swals.fire({
            title: `ni entar kasih kata-kata ndiri &#129303`,
            confirmButtonText: "okayy",
          });
          setTimeout(this.showDiv, 100);
        }
      }
    },
    nonDiv() {
      document.getElementById("konten").style.opacity = "0";
    },
    showDiv() {
      document.getElementById("konten").style.opacity = "1";
      document.getElementById("konten").style.top = "0";
      document.querySelector("body").style.animation = "anim 9s ease infinite";
    },
    tombol() {
      document.getElementById("buttonWa").style.margin = "0";
      document.getElementById("buttonWa").style.opacity = "1";
    },
    klikfoto() {
      document.getElementById("sp1").style.display = "none";
      document.getElementById("sp2").style.display = "block";
      if (this.a < this.finish.length) {
        document.getElementById("finish").innerHTML += this.finish.charAt(
          this.a
        );
        this.a++;
        setTimeout(this.klikfoto, 100);
      }
      if (this.a == this.finish.length) {
        setTimeout(this.tombol, 500);
      }
    },
    bukaWa() {
      window.location =
        "https://api.whatsapp.com/send?phone=6281214586283&text=ini button wa dari web testing";
    },
  },
};
</script>

<style scoped>
*,
body,
html {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  transition: all 0.3s ease;
  font-family: "Poppins", sans-serif;
  padding: 25px;
}

a {
  text-decoration: none;
}

.button:hover {
  transform: scale(0.9);
}

.foto {
  display: block;
  text-align: center;
  width: 100%;
  height: 150px;
}

.foto > * {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
  color: white;
}

.foto img {
  border-radius: 20%;
  transition: all 0.3s ease;
}

.foto img:first-child {
  z-index: 1;
}

#buttonWa {
  margin-top: 100px;
  opacity: 0;
  /* background: #fff; */
  padding-bottom: 120px;
  transition: all 0.5s ease;
  display: flex;
  justify-content: center;
  align-items: center;
  list-style: none;
}

.icon {
  flex-shrink: 0;
  display: inline-block;
  margin-right: 12px;
  width: 18px;
  height: 18px;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

.icon.whatsapp {
  background-image: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32' fill='%23fefefe'><g><path d='M16,2A13,13,0,0,0,8,25.23V29a1,1,0,0,0,.51.87A1,1,0,0,0,9,30a1,1,0,0,0,.51-.14l3.65-2.19A12.64,12.64,0,0,0,16,28,13,13,0,0,0,16,2Zm0,24a11.13,11.13,0,0,1-2.76-.36,1,1,0,0,0-.76.11L10,27.23v-2.5a1,1,0,0,0-.42-.81A11,11,0,1,1,16,26Z'/><path d='M19.86,15.18a1.9,1.9,0,0,0-2.64,0l-.09.09-1.4-1.4.09-.09a1.86,1.86,0,0,0,0-2.64L14.23,9.55a1.9,1.9,0,0,0-2.64,0l-.8.79a3.56,3.56,0,0,0-.5,3.76,10.64,10.64,0,0,0,2.62,4A8.7,8.7,0,0,0,18.56,21a2.92,2.92,0,0,0,2.1-.79l.79-.8a1.86,1.86,0,0,0,0-2.64Zm-.62,3.61c-.57.58-2.78,0-4.92-2.11a8.88,8.88,0,0,1-2.13-3.21c-.26-.79-.25-1.44,0-1.71l.7-.7,1.4,1.4-.7.7a1,1,0,0,0,0,1.41l2.82,2.82a1,1,0,0,0,1.41,0l.7-.7,1.4,1.4Z'/></g></svg>");
}

.button {
  margin-top: 12px;
  transition: all 0.2s ease;
  display: inline-flex;
  align-items: center;
  padding: 10px 15px;
  outline: 0;
  border: 0;
  border-radius: 10px;
  line-height: 20px;
  color: #fefefe;
  background: green;
  font-size: 13px;
  white-space: nowrap;
  overflow: hidden;
  max-width: 100%;
}

#konten {
    padding-top: 40px;
  position: relative;
  transition: all 3s ease;
  opacity: 0;
}

@keyframes halo {
  0% {
    left: -24px;
    top: 0;
  }

  50% {
    left: -20px;
    top: 0px;
  }

  100% {
    left: -24px;
    top: 0px;
  }
}

</style>
