<template>
  <section
    class="bg-gradient-to-b px-10 xl:py-20 py-10 from-[#101010] via-transparent to-[#101010] flex-col xl:gap-y-8 gap-y-5 justify-center flex items-center w-full h-full"
  >
    <h1
      class="xl:text-7xl md:text-5xl text-3xl font-bold uppercase mx-auto text-center text-white"
      style="font-family: 'Josefin Sans Variable'"
    >
      try your hands on
    </h1>
    <div
      class="flex flex-wrap max-w-7xl mx-auto w-full h-auto xl:justify-between justify-center items-center gap-10"
    >
      <div
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
</template>
<script setup>
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
