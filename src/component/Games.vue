<template>
  <section
    class="bg-gradient-to-b px-10 xl:py-20 py-10 from-[#101010] via-[#000000] to-[#101010] flex-col xl:gap-y-8 gap-y-5 justify-center flex items-center w-full h-full"
  >
    <h1
      ref="tittleSection"
      class="xl:text-7xl md:text-5xl text-3xl font-bold uppercase mx-auto text-center text-white"
      style="font-family: 'Josefin Sans Variable'"
    >
      try your hands on
    </h1>
    <div
      class="flex flex-wrap max-w-7xl mx-auto w-full h-auto xl:justify-between justify-center items-center gap-10"
    >
      <div
        ref="cards"
        v-for="(item, index) in gamesList"
        :key="index"
        class="flex-col justify-end relative w-auto h-auto flex items-center"
      >
        <img :src="item.image" class="w-auto h-auto object-cover object-center" />
        <div
          class="flex justify-between absolute p-6 bg-white backdrop-blur-md bg-opacity-5 items-center w-full"
        >
          <p
            class="text-white xl:text-xl font-light md:text-lg text-base"
            style="font-family: 'Open Sans Variable'"
          >
            {{ item.stream }}
          </p>
          <span class="bg-green-500 p-1.5 rounded-full"></span>
        </div>
      </div>
    </div>
  </section>
  <div class="absolute w-11/12 h-full z-0 flex justify-start items-start">
    <div
      class="bg-[#BA62FF] bg-opacity-30 rotate-12 blur-3xl -z-20 rounded-full w-1/2 h-1/2 overflow-hidden"
    ></div>
  </div>
</template>
<script setup>
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/all'
import { onMounted, ref } from 'vue'

const tittleSection = ref(null)
const cards = ref([])
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
        start: 'top bottom',
        end: 'bottom top',
        scrub: false,
        toggleActions: 'play reverse play reverse'
      }
    }
  )
  cards.value.forEach((child) => {
    gsap.fromTo(
      child,
      { opacity: 0, y: 30 },
      {
        opacity: 1,
        y: 0,
        duration: 1,
        stagger: 0.3,
        delay: 0.7,
        ease: 'power3.out',
        scrollTrigger: {
          trigger: child,
          start: 'top bottom',
          end: 'bottom top',
          scrub: false,
          toggleActions: 'play reverse play reverse'
        }
      }
    )
  })
}

onMounted(() => {
  animateOnScroll()
})

const gamesList = [
  {
    image: '/codbo.png',
    stream: '28 Streaming'
  },
  {
    image: '/pubg.png',
    stream: '365 Streaming'
  },
  {
    image: '/fortnite.png',
    stream: '12 Streaming'
  },
  {
    image: '/amogus.png',
    stream: '62 Streaming'
  },
  {
    image: '/rdr II.png',
    stream: '3 Streaming'
  },
  {
    image: '/gta v.png',
    stream: '43 Streaming'
  }
]
</script>
