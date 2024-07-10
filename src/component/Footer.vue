<template>
  <footer ref="footerSection" class="w-full bg-[#101010] border-t-black border-t-[2px]">
    <div
      style="font-family: 'Josefin Sans Variable'"
      class="flex px-7 md:px-14 lg:px-16 py-5 md:py-8 xl:px-0 xl:max-w-7xl xl:mx-auto justify-between items-center w-full text-white"
    >
      <div
        class="flex justify-center text-slate-400 xl:text-lg sm:text-base text-xs text-center font-medium items-center gap-x-5 xl:gap-x-10"
      >
        <p>Privacy policy</p>
        <p>Terms & Condition</p>
      </div>
      <p class="text-slate-400 xl:text-lg sm:text-base text-xs text-center font-medium">
        Copyright © <span class="text-white">Gruxz</span>
      </p>
    </div>
  </footer>
</template>
<script setup>
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/all'
import { onMounted, ref } from 'vue'

const footerSection = ref(null)
gsap.registerPlugin(ScrollTrigger)

const animateOnScroll = () => {
  gsap.fromTo(
    footerSection.value,
    { opacity: 0, y: 30 },
    {
      opacity: 1,
      y: 0,
      duration: 1,
      stagger: 0.3,
      delay: 0.2,
      ease: 'power3.out',
      scrollTrigger: {
        trigger: footerSection.value,
        start: 'center bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
      }
    }
  )
}

onMounted(() => {
  animateOnScroll()
})
</script>
