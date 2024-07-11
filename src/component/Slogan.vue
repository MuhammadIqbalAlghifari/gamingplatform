<template>
  <div class="absolute w-11/12 h-full -z-10 flex justify-end items-start">
    <div
      class="bg-[#BA62FF] bg-opacity-30 rotate-12 blur-3xl -z-20 rounded-full w-1/2 h-1/2 overflow-hidden"
    ></div>
  </div>
  <section
    class="bg-gradient-to-b px-10 from-[#101010] via-transparent to-[#101010] flex-col xl:gap-y-10 gap-y-5 justify-center flex items-center w-full h-auto"
  >
    <div
      class="w-full h-full my-32 flex flex-col gap-y-5 lg:gap-y-0 lg:flex-row justify-center items-center"
    >
      <div
        ref="leftSection"
        class="flex-col lg:mx-auto xl:mx-0 gap-y-5 flex lg:justify-end justify-center h-auto lg:-mb-96 xl:-mr-48 lg:-mr-80 lg:items-start items-center z-10"
      >
        <h1
          class="xl:text-[80px] md:text-5xl text-3xl text-white lg:text-start text-center font-bold uppercase leading-none w-full lg:max-w-[18rem] xl:max-w-xs"
          style="font-family: 'Josefin Sans Variable'"
        >
          SHOW YOUR TALENT
        </h1>
        <p
          class="xl:text-xl md:text-lg text-sm w-full lg:max-w-sm mx-auto font-light lg:text-start text-center text-white"
          style="font-family: 'Open Sans Variable'"
        >
          Mauris blandit aliquet elit, eget tincidunt nibh pulvinar a. Donec rutrum congue leo eget
          malesuada. Vivamus magna justo.
        </p>
        <button
          style="font-family: 'Josefin Sans Variable'"
          class="flex justify-center items-center md:gap-x-2 gap-x-0.5 xl:text-xl md:text-base text-sm text-white font-semibold"
        >
          Start Streaming
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="text-[#8F00FF]"
            width="2em"
            height="2em"
            viewBox="0 0 24 24"
          >
            <path
              fill="none"
              stroke="currentColor"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M19 12H5m14 0l-4 4m4-4l-4-4"
            />
          </svg>
        </button>
      </div>
      <img
        ref="imageSection"
        src="/joystick.png"
        alt=""
        class="w-auto z-0 h-auto object-center object-cover"
      />
      <div
        ref="rightSection"
        class="flex-col xl:gap-y-14 gap-y-5 flex h-full justify-start -mt-20 lg:-ml-36 xl:mt-1 lg:-mt-56 items-center z-10"
      >
        <h1
          class="xl:text-[80px] md:text-6xl text-4xl text-white lg:text-start text-center font-bold uppercase leading-none w-full lg:max-w-xs"
          style="font-family: 'Josefin Sans Variable'"
        >
          Play record share
        </h1>
        <div
          class="lg:flex-col flex-row flex justify-center h-auto lg:-ml-10 xl:gap-y-10 gap-y-5 lg:items-start items-center lg:gap-y-0 gap-x-10"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="text-white bg-[#8F00FF] xl:size-[4em] size-[2em] rounded-full xl:p-2 p-1"
            viewBox="0 0 24 24"
          >
            <g
              fill="none"
              stroke="currentColor"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
            >
              <path
                d="M5.636 5.636a9 9 0 0 1 13.397.747L13.414 12l5.619 5.617A9 9 0 1 1 5.636 5.636"
              />
              <circle cx="11.5" cy="7.5" r="1" fill="currentColor" />
            </g>
          </svg>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="text-white bg-[#8F00FF] xl:size-[4em] size-[2em] rounded-full xl:p-2 p-1"
            viewBox="0 0 32 32"
          >
            <path
              fill="currentColor"
              d="M16 25a9 9 0 1 0 0-18a9 9 0 0 0 0 18m0-23C8.268 2 2 8.268 2 16s6.268 14 14 14s14-6.268 14-14S23.732 2 16 2M4 16C4 9.373 9.373 4 16 4s12 5.373 12 12s-5.373 12-12 12S4 22.627 4 16"
            />
          </svg>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="text-white bg-[#8F00FF] xl:size-[4em] size-[2em] rounded-full xl:p-2 p-1"
            viewBox="0 0 24 24"
          >
            <path
              fill="currentColor"
              d="M18 22q-1.25 0-2.125-.875T15 19q0-.175.025-.363t.075-.337l-7.05-4.1q-.425.375-.95.588T6 15q-1.25 0-2.125-.875T3 12t.875-2.125T6 9q.575 0 1.1.213t.95.587l7.05-4.1q-.05-.15-.075-.337T15 5q0-1.25.875-2.125T18 2t2.125.875T21 5t-.875 2.125T18 8q-.575 0-1.1-.212t-.95-.588L8.9 11.3q.05.15.075.338T9 12t-.025.363t-.075.337l7.05 4.1q.425-.375.95-.587T18 16q1.25 0 2.125.875T21 19t-.875 2.125T18 22m0-16q.425 0 .713-.287T19 5t-.288-.712T18 4t-.712.288T17 5t.288.713T18 6M6 13q.425 0 .713-.288T7 12t-.288-.712T6 11t-.712.288T5 12t.288.713T6 13m12 7q.425 0 .713-.288T19 19t-.288-.712T18 18t-.712.288T17 19t.288.713T18 20m0-1"
            />
          </svg>
        </div>
      </div>
    </div>
  </section>
</template>
<script setup>
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/all'
import { onMounted, ref } from 'vue'

const leftSection = ref(null)
const rightSection = ref(null)
const imageSection = ref(null)
gsap.registerPlugin(ScrollTrigger)

const animateOnScroll = () => {
  leftSection.value.childNodes.forEach((child) => {
    gsap.fromTo(
      child,
      { opacity: 0, y: 30 },
      {
        opacity: 1,
        y: 0,
        duration: 1,
        stagger: 0.3,
        delay: 0.2,
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
  rightSection.value.childNodes.forEach((child) => {
    gsap.fromTo(
      child,
      { opacity: 0, y: 30 },
      {
        opacity: 1,
        y: 0,
        duration: 1,
        stagger: 0.3,
        delay: 0.2,
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
  gsap.fromTo(
    imageSection.value,
    { opacity: 0 },
    {
      opacity: 1,
      duration: 1,
      stagger: 0.3,
      delay: 1,
      ease: 'power3.out',
      scrollTrigger: {
        trigger: imageSection.value,
        start: 'top bottom',
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
