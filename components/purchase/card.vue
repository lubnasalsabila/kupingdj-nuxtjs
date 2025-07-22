<template>
  <div
    class="relative border cursor-pointer overflow-hidden bg-no-repeat bg-right bg-contain transition-transform duration-300 hover:-translate-y-1 
           w-[280px] h-[280px] sm:scale-100 scale-[0.75] origin-top-left"
    style="background-image: url('/images/back-purchase.svg')"
  >
    <!-- Logo kiri atas -->
    <div class="absolute top-6 left-6">
      <img :src="purchase" :alt="title" class="w-[72px] h-[72px] sm:w-[72px] sm:h-[72px]" />
    </div>

    <!-- Teks judul -->
    <div class="absolute bottom-5 left-5 text-black font-bold tracking-wide uppercase text-2xl sm:text-3xl">
      {{ title }}
    </div>
  </div>
</template>

<script setup>
defineProps({
  purchase: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  }
})
</script>
