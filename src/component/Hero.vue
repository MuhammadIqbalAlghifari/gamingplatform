<template>
  <section
    class="bg-gradient-to-b px-10 from-[#101010] via-transparent to-[#101010] justify-center flex items-center w-full h-screen"
  >
    <img
      src="/Hero Image.jpg"
      class="w-full h-full object-cover object-center brightness-50 fixed -z-50"
    />
    <div
      ref="heroSection"
      class="flex-col xl:gap-y-8 gap-y-5 justify-center flex items-center w-full h-screen"
    >
      <h1
        class="xl:text-7xl md:text-5xl text-3xl max-w-[35rem] font-bold uppercase mx-auto text-center text-white"
        style="font-family: 'Josefin Sans Variable'"
      >
        A Community For Gamers by Gamers
      </h1>
      <p
        class="xl:text-xl md:text-lg text-sm max-w-xs mx-auto font-light text-center text-white"
        style="font-family: 'Open Sans Variable'"
      >
        Meet, network, make new friends and play together
      </p>
      <div class="flex justify-center items-center gap-x-5">
        <button
          style="font-family: 'Open Sans Variable'"
          class="bg-gradient-to-r flex justify-center items-center md:gap-x-2 gap-x-0.5 from-[#8F00FF] to-[#C478FF] xl:text-xl md:text-base sm:text-sm text-xs md:px-6 md:py-2 px-3 py-1 text-white font-medium"
        >
          Join Now
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="1.5em"
            height="1.5em"
            viewBox="0 0 256 256"
          >
            <path
              fill="currentColor"
              d="M200 64v104a8 8 0 0 1-16 0V83.31L69.66 197.66a8 8 0 0 1-11.32-11.32L172.69 72H88a8 8 0 0 1 0-16h104a8 8 0 0 1 8 8"
            />
          </svg>
        </button>
        <button
          class="border-[3px] border-[#8F00FF] bg-transparent xl:text-xl md:text-base sm:text-sm text-xs md:px-6 md:py-2 px-3 py-1 text-white font-medium"
          style="font-family: 'Josefin Sans Variable'"
        >
          How It Works
        </button>
      </div>
    </div>
  </section>
</template>
<script setup>
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/all'
import { onMounted, ref } from 'vue'

const heroSection = ref(null)
gsap.registerPlugin(ScrollTrigger)

const animateOnScroll = () => {
  gsap.fromTo(
    heroSection.value.children,
    { opacity: 0, y: 30 },
    {
      opacity: 1,
      y: 0,
      duration: 1,
      stagger: 0.3,
      delay: 0.2,
      ease: 'power3.out',
      scrollTrigger: {
        trigger: heroSection.value.children,
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
