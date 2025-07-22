<template>
  <div
    class="relative w-[233px] h-[308px] border cursor-pointer overflow-hidden bg-no-repeat bg-right bg-contain transition-transform duration-300 hover:-translate-y-1"
    style="background-image: url('/images/back-card-explore.svg')"
  >
    <!-- Logo di kiri atas -->
    <div class="absolute top-6 left-6">
      <img :src="genre" :alt="genrename" class="w-[99px] h-[99px]" />
    </div>

    <!-- Nama genre -->
    <div class="absolute bottom-5 left-5 text-black font-bold text-[32px] tracking-wide uppercase">
      {{ genrename }}
    </div>

    <!-- Ikon panah -->
    <div class="absolute bottom-7 right-7 w-[24px] h-[24px]">
      <img src="/images/arrow-black.svg" alt="arrow" class="w-full h-full object-contain" />
    </div>
  </div>
</template>

<script setup>
defineProps({
    genre: {
        type: String,
        required: true
    },
    genrename: {
        type: String,
        required: true
    },
})
</script>
