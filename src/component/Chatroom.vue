<template>
  <section
    class="bg-gradient-to-b px-10 from-[#101010] via-transparent to-[#101010] justify-center flex items-center w-full h-screen"
  >
    <img
      src="/classic.jpg"
      class="w-full h-full object-cover object-center brightness-50 absolute -z-50"
    />
    <div
      ref="chatroomSection"
      class="flex-col xl:gap-y-8 gap-y-5 justify-center flex items-center w-full h-screen"
    >
      <h1
        class="xl:text-7xl md:text-5xl text-3xl max-w-2xl font-bold uppercase mx-auto text-center text-white"
        style="font-family: 'Josefin Sans Variable'"
      >
        make new friends and play with them
      </h1>
      <button
        style="font-family: 'Open Sans Variable'"
        class="bg-gradient-to-r md:gap-x-2 gap-x-0.5 from-[#8F00FF] to-[#C478FF] xl:text-xl md:text-base text-sm md:px-6 md:py-2 px-3 py-1 text-white font-medium"
      >
        Join Chatrooms
      </button>
    </div>
  </section>
</template>
<script setup>
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/all'
import { onMounted, ref } from 'vue'

const chatroomSection = ref(null)
gsap.registerPlugin(ScrollTrigger)

const animateOnScroll = () => {
  gsap.fromTo(
    chatroomSection.value.children,
    { opacity: 0, y: 30 },
    {
      opacity: 1,
      y: 0,
      duration: 1,
      stagger: 0.3,
      delay: 0.2,
      ease: 'power3.out',
      scrollTrigger: {
        trigger: chatroomSection.value.children,
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
