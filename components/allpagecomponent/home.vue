<template>
  <div class="relative min-h-screen overflow-hidden bg-white">
        <!-- Pink shadow background -->
        <div class="absolute top-0 left-0 w-full h-full z-0">
        <img 
            src="/images/red-shadow-home.svg" 
            alt="pink shadow"
            class="w-lg h-lg object-cover"
        />
        </div>

        <!-- Red wave lines background -->
        <div class="absolute top-0 left-0 w-full h-full z-5">
        <img 
            src="/images/latar-home.svg" 
            alt="red wave lines"
            class="w-lg h-lg object-cover"
        />
        </div>

    <!-- Main content container -->
    <div class="relative z-20 flex h-screen mb-5">
      
      <!-- Left section - Hero text and stats -->
      <div class="flex-1 px-12 py-20 flex flex-col justify-center">
        
        <!-- Main hero text -->
        <div class="mb-14">
          <h1 class="text-6xl font-bold text-black leading-tight">
            DISCOVER THE<br />
            ULTIMATE<br />
            DJ MARKETPLACE<br />
            EXPERIENCE!
          </h1>
        </div>

        <!-- Stats section -->
        <div class="flex gap-16 mb-10">
          <IndexBest />
          <IndexMix />
          <IndexAlbum />
        </div>

        <!-- Scroll down text -->
        <div class="flex items-center gap-3 mb-4">
          <span class="text-black text-lg font-medium">SCROLL DOWN</span>
          <div class="w-6 h-6 flex items-center justify-center">
            <img src="/images/mouse.svg" alt="" class="w-6 h-6">
          </div>
        </div>

      </div>

      <!-- Right section - Vinyl record -->
      <div class="flex-1 relative flex items-center justify-center">
        <img 
          src="/images/piringhitam-home.png" 
          alt="Vinyl Record"
          class="w-auto h-[600px] object-contain"
        />
        
        
      </div>

    </div>

    <!-- Bottom scrolling banner -->
    <div class="absolute bottom-0 left-0 z-10">
      <!-- Label component positioned on vinyl -->
        <IndexLabelRed />
    </div>

  </div>
</template>

<script setup>

</script>

<style scoped>

</style>