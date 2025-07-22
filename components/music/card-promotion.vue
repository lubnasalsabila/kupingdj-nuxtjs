<template>
  <div class="w-[160px] h-[137px] border border-gray-300 overflow-hidden text-sm flex flex-col justify-between">
    <!-- Top: Icon -->
    <div class="px-2 pt-2 pb-3">
      <img src="/images/red-file.svg" alt="Play" class="w-5 h-5" />
    </div>

    <!-- Title -->
    <div class="px-2 pt-4">
      <p class="font-semibold text-black leading-tight text-xs">Promotion Video</p>
      <!-- Date & Size -->
      <div class="text-gray-500 text-[10px] flex gap-1 items-center">
        <span>{{ date }}</span>
        <span>• {{ capacity }}</span>
      </div>
    </div>

    

    <!-- Download Bar -->
    <div class="bg-[#A10501] text-white flex justify-between items-center px-2 py-1">
      <span class="text-[11px] font-semibold">Download</span>
      <img src="/images/download-white.svg" alt="Cart" class="w-4 h-4" />
    </div>
  </div>
</template>

<script setup>
defineProps({
  date: String,
  capacity: String
})
</script>

<style scoped></style>
