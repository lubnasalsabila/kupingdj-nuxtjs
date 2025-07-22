<template>
  <div
    class="relative w-[280px] h-[280px] border cursor-pointer overflow-hidden bg-no-repeat bg-right bg-contain transition-transform duration-300 hover:-translate-y-1"
    style="background-image: url('/images/back-purchase.svg')"
  >
    <!-- Logo di kiri atas -->
    <div class="absolute top-6 left-6">
      <img :src="purchase" :alt="title" class="w-[72px] h-[72px]" />
    </div>

    <!-- Nama genre -->
    <div class="absolute bottom-5 left-5 text-black font-bold text-3xl tracking-wide uppercase">
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
    },
})
</script>
