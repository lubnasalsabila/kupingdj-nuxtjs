<template>
  <div class="w-[160px] h-[137px] border border-gray-300 overflow-hidden text-sm flex flex-col justify-between">
    <!-- Top: Play Button, Progress, Duration -->
    <div class="px-2 pt-2 pb-3">
      <div class="flex items-center gap-1 mb-1">
        <img src="/images/playbtn-black.svg" alt="Play" class="w-5 h-5" />
        <div class="h-1 bg-gray-200 w-full">
          <div class="w-1/4 h-full bg-[#A10501]"></div>
        </div>
      </div>
      <span class="text-[10px] text-gray-600 block leading-none">{{ duration }}</span>
    </div>

    <!-- Title -->
    <div class="px-2">
      <p class="font-semibold text-black leading-tight text-xs line-clamp-2">{{ title }}</p>
        <!-- Date & Size -->
      <div class="text-gray-500 text-[10px] flex gap-1 items-center">
        <span>{{ date }}</span>
        <span>• {{ capacity }}</span>
      </div>
    </div>

    

    <!-- Price Bar -->
    <div class="bg-[#A10501] text-white flex justify-between items-center px-2 py-1">
      <span class="text-[11px] font-semibold">Rp. {{ price }}</span>
      <img src="/images/add-chart-white.svg" alt="Cart" class="w-4 h-4" />
    </div>
  </div>
</template>

<script setup>
defineProps({
  duration: String,
  title: String,
  date: String,
  capacity: String,
  price: String
})
</script>

<style scoped></style>
