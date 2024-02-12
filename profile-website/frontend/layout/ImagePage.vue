<template>
  <div class="overflow-hidden">
    <div ref="triggerRef">
      <div ref="sectionRef" class="h-screen w-[400vw] flex flex-row relative">
        <div class="h-screen w-[100vw] flex justify-center items-center">
          <h3>section 1</h3>
        </div>
        <div class="h-screen w-[100vw] flex justify-center items-center">
          <h3>section 2</h3>
        </div>
        <div class="h-screen w-[100vw] flex justify-center items-center">
          <h3>section 3</h3>
        </div>
        <div class="h-screen w-[100vw] flex justify-center items-center">
          <h3>section 4</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
import { ref, onMounted, onBeforeUnmount } from "vue";

export default {
  setup() {
    const sectionRef = ref(null);
    const triggerRef = ref(null);

    gsap.registerPlugin(ScrollTrigger);

    onMounted(() => {
      const pin = gsap.fromTo(
        sectionRef.value,
        {
          translateX: 0,
        },
        {
          translateX: "-300vw",
          ease: "none",
          duration: 1,
          scrollTrigger: {
            trigger: triggerRef.value,
            start: "top top",
            end: "2000 top",
            scrub: 0.6,
            pin: true,
          },
        }
      );

      onBeforeUnmount(() => {
        pin.kill();
      });
    });

    return {
      sectionRef,
      triggerRef,
    };
  },
};
</script>

<style scoped>
/* Your styles go here */
</style>
