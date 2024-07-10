<template>
  <div
    :class="[
      'absolute top-0 left-0 h-screen w-screen bg-[#0a0606] transform transition-transform duration-300 ease-in-out filter drop-shadow-md',
      open ? '-translate-y-0' : '-translate-y-full'
    ]"
  >
    <div
      class="flex flex-col items-center justify-center lg:gap-y-4 gap-y-2 py-10 xl:text-lg text-base text-black"
    >
      <p
        class="hover:text-white text-slate-400 cursor-pointer font-bold transition-all duration-300"
        to="/"
        @click="setOpen(false)"
      >
        Drop
      </p>
      <p
        class="hover:text-white text-slate-400 cursor-pointer font-bold transition-all duration-300"
        to="/about"
        @click="setOpen(false)"
      >
        Marketplace
      </p>
      <p
        class="hover:text-white text-slate-400 cursor-pointer font-bold transition-all duration-300"
        to="/portfolio"
        @click="setOpen(false)"
      >
        Creator
      </p>
      <p
        class="hover:text-white text-slate-400 cursor-pointer font-bold transition-all duration-300"
        to="/news"
        @click="setOpen(false)"
      >
        Community
      </p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  open: Boolean
})

const emit = defineEmits(['set-open'])

const setOpen = (val) => {
  emit('set-open', val)
}
</script>
