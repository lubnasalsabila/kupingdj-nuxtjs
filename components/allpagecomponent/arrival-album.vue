<template>
  <div class="pt-14 px-10">
    <!-- Title -->
    <h1 class="text-4xl text-black mb-8 text-glancyr uppercase font-normal">NEW ARRIVAL ALBUM</h1>

    <!-- Horizontal Scroll Album Wrapper -->
    <div class="flex gap-4 overflow-x-auto pb-4">
      <!-- Album Cards Container -->
      <div class="flex gap-4 min-w-max">
        <!-- Album 1 -->
        <div class="flex gap-4 border border-gray-300 p-4 w-[670px]">
          <!-- Album Cover -->
          <div class="flex-shrink-0">
            <MusicCardMusic 
              album-cover="/images/blues.png" 
              title="Blues. Album Exclusive On Kuping DJ" 
              date="02 July, 2025" 
              price="Rp. 200,000 (bundling Price)" 
            />
          </div>

          <!-- Tracks Grid -->
          <div class="flex-1 max-h-[476px] overflow-y-auto">
            <div class="grid grid-cols-2 gap-2">
              <MusicCardPromotion 
                date="03, Jul 2025" 
                capacity="80 Mb" 
              />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 1" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 2" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 3" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 4" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 5" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 6" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 7" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
            </div>
          </div>
        </div>

        <!-- Album 2 -->
        <div class="flex gap-4 border border-gray-300 p-4 w-[670px]">
          <!-- Album Cover -->
          <div class="flex-shrink-0">
            <MusicCardMusic 
              album-cover="/images/youandme.png" 
              title="You And Me. Album Exclusive On Kuping DJ" 
              date="02 July, 2025" 
              price="Rp. 200,000 (bundling Price)" 
            />
          </div>

          <!-- Tracks Grid -->
          <div class="flex-1 max-h-[476px] overflow-y-auto">
            <div class="grid grid-cols-2 gap-2">
              <MusicCardPromotion 
                date="03, Jul 2025" 
                capacity="80 Mb" 
              />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 1" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 2" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 3" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 4" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 5" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 6" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
              <MusicCardPlay duration="3 Min, 20 Sec" title="Music 7" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Explore button -->
    <div class="container mx-auto px-4 mt-12 flex justify-center">
      <button
        class="flex items-center text-white font-semibold uppercase transition-colors"
      >
        <span class="bg-[#A10501] px-6 py-4 text-base">EXPLORE ALL ALBUM</span>
        <span class="bg-black px-4 py-4 flex items-center justify-center">
          <img src="/images/arrow-white.svg" alt="arrow" class="w-6 h-6" />
        </span>
      </button>
    </div>
  </div>
</template>

<script setup>
</script>

<style scoped>
</style>
