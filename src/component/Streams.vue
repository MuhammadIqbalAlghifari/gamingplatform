<template>
  <div class="absolute w-11/12 h-full -z-10 flex justify-end items-start">
    <div
      class="bg-[#BA62FF] bg-opacity-30 rotate-12 blur-3xl -z-20 rounded-full w-1/2 h-1/2 overflow-hidden"
    ></div>
  </div>
  <section
    class="bg-gradient-to-b px-10 from-[#101010] via-[#000000] to-[#101010] flex-col xl:gap-y-10 gap-y-5 justify-center flex items-center w-full h-auto"
  >
    <div
      class="w-full h-full my-32 flex lg:flex-row flex-col lg:gap-y-0 justify-center items-start"
    >
      <!-- <div class="flex-col gap-y-5 flex justify-start h-auto items-start z-10 absolute max-w-2xl"> -->
      <h1
        ref="tittleSection"
        class="xl:text-[80px] md:text-5xl text-3xl text-white lg:text-start -mb-10 text-center font-bold uppercase lg:absolute max-w-2xl z-10 lg:-ml-48 xl:-mt-14 lg:-mb-14 leading-none"
        style="font-family: 'Josefin Sans Variable'"
      >
        watch top pick streams
      </h1>
      <!-- </div> -->
      <img
        src="/stream.png"
        ref="imageSection"
        alt=""
        class="w-auto z-0 h-auto object-center object-cover"
      />
    </div>
  </section>
</template>
<script setup>
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/all'
import { onMounted, ref } from 'vue'

const tittleSection = ref(null)
const imageSection = ref(null)
gsap.registerPlugin(ScrollTrigger)

const animateOnScroll = () => {
  gsap.fromTo(
    tittleSection.value,
    { opacity: 0, y: 30 },
    {
      opacity: 1,
      y: 0,
      duration: 1,
      stagger: 0.3,
      delay: 0.5,
      ease: 'power3.out',
      scrollTrigger: {
        trigger: tittleSection.value,
        start: 'center bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
      }
    }
  )
  gsap.fromTo(
    imageSection.value,
    { opacity: 0 },
    {
      opacity: 1,
      duration: 1,
      stagger: 0.3,
      delay: 0.2,
      ease: 'power3.out',
      scrollTrigger: {
        trigger: imageSection.value,
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
