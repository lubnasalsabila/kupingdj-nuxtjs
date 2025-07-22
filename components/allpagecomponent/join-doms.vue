<template>
  <div class="relative px-10 mt-32 overflow-hidden">
    <!-- Gradient Background Layer -->
    <div class="absolute inset-0 z-0" 
         style="background: linear-gradient(to right, #A10501, #740000);">
    </div>

    <!-- Image Background Layer -->
    <div class="absolute inset-0 z-0 bg-center bg-no-repeat bg-cover" 
         style="background-image: url('/images/back-right-home.svg');">
    </div>

    <!-- Content Layer -->
    <div class="relative z-10 flex">
      <div class="right pt-14">
        <h1 class="uppercase text-5xl text-white text-glancyr uppercase font-normal">
          join DOMS STATION, <br />
          The new era Indonesian DJ Education Culture!
        </h1>
        <button class="flex items-center font-semibold uppercase transition-colors mt-6 py-6">
          <span class="bg-white px-6 py-4 text-xl uppercase">doms station website</span>
          <span class="bg-black px-4 py-4 flex items-center justify-center">
            <img src="/images/arrow-white.svg" alt="arrow" class="w-7 h-7" />
          </span>
        </button>
        <div class="flex gap-4 pt-16">
            <button><img src="/images/play-btn.svg" alt=""></button>
            <button><img src="/images/app-btn.svg" alt=""></button>
        </div>
      </div>
      <img src="/images/mobile.png" alt="" />
    </div>

    </div>
<IndexLabelBlack />
</template>



<script setup>

</script>

<style lang="scss" scoped>

</style>