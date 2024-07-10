<template>
  <header
    ref="navbarRef"
    :class="[
      'fixed z-50 w-full transition-colors duration-300',
      isScrolled ? 'bg-black bg-opacity-30 backdrop-blur-md border-none' : 'bg-transparent'
    ]"
  >
    <nav
      class="flex px-7 md:px-14 lg:px-16 py-5 md:py-8 xl:px-0 xl:max-w-7xl xl:mx-auto justify-between items-center w-full text-white"
    >
      <MobileNav :open="open" @set-open="setOpen" />
      <p
        class="transition-all flex duration-300 font-bold lg:text-3xl text-xl text-transparent bg-clip-text bg-gradient-to-br from-[#8F00FF] to-[#FFFFFF]"
        style="font-family: 'Josefin Sans Variable'"
      >
        Gruxz
      </p>
      <div
        class="justify-between xl:w-[35%] xl:gap-x-0 md:gap-x-4 hidden md:flex items-center xl:text-lg text-base"
      >
        <p
          class="transition-all duration-300 hover:text-white text-slate-400 font-bold cursor-pointer"
          style="font-family: 'Josefin Sans Variable'"
        >
          Home
        </p>
        <p
          class="transition-all duration-300 hover:text-white text-slate-400 font-bold cursor-pointer"
          style="font-family: 'Josefin Sans Variable'"
        >
          Streams
        </p>
        <p
          class="transition-all duration-300 hover:text-white text-slate-400 font-bold cursor-pointer"
          style="font-family: 'Josefin Sans Variable'"
        >
          Competitions
        </p>
        <p
          class="transition-all duration-300 hover:text-white text-slate-400 font-bold cursor-pointer"
          style="font-family: 'Josefin Sans Variable'"
        >
          Pricing
        </p>
      </div>
      <div
        class="flex relative w-10 h-5 flex-col justify-between items-end cursor-pointer"
        @click="toggleOpen"
      >
        <span
          :class="[
            'h-0.5 rounded-lg transform transition duration-500 ease-out',
            open ? 'rotate-45 translate-y-1 bg-white w-10' : 'bg-white w-5'
          ]"
        ></span>
        <span
          :class="[
            'h-0.5 rounded-lg transform transition-all duration-500 ease-out',
            open ? 'w-0 h-0' : 'bg-white w-full'
          ]"
        ></span>
        <span
          :class="[
            'h-0.5 rounded-lg transform transition duration-500 ease-out',
            open ? '-rotate-45 w-full -translate-y-3.5 bg-white' : 'bg-white w-7'
          ]"
        ></span>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import gsap from 'gsap'
import MobileNav from './MobileNav.vue'

const open = ref(false)
const isScrolled = ref(false)
const navbarRef = ref(null)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const setOpen = (val) => {
  open.value = val
}

const toggleOpen = () => {
  open.value = !open.value
}

onMounted(() => {
  gsap.fromTo(navbarRef.value, { opacity: 0, y: -100 }, { opacity: 1, y: 0, duration: 1.5 })
  window.addEventListener('scroll', handleScroll)
  return () => {
    window.removeEventListener('scroll', handleScroll)
  }
})

onBeforeUnmount(() => {})
</script>

<style>
.router-link-active {
  color: orange;
}
</style>
