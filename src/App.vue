<template>
  <Navbar />
  <Hero />
  <Slogan />
  <Chatroom />
  <Games />
  <Streams />
  <Community />
  <Footer />
</template>
<script setup>
import Navbar from './component/Navbar.vue'
import Hero from './component/Hero.vue'
import Slogan from './component/Slogan.vue'
import Chatroom from './component/Chatroom.vue'
import Community from './component/Community.vue'
import Streams from './component/Streams.vue'
import Footer from './component/Footer.vue'
import Games from './component/Games.vue'
import { onMounted } from 'vue'
import Lenis from 'lenis'

onMounted(() => {
  const lenis = new Lenis()

  function raf(time) {
    lenis.raf(time)
    requestAnimationFrame(raf)
  }

  requestAnimationFrame(raf)
})
</script>
