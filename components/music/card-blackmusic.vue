<template>
  <!-- Responsive Container -->
  <div class="max-w-[315px] w-full origin-top scale-100 sm:scale-[0.9] xs:scale-[0.8]">

    <!-- Main card content -->
    <div class="relative z-10 p-4 sm:p-6">

      <!-- Album Cover with Vinyl disc -->
      <div class="relative w-full max-w-[234px] mb-2">
        <!-- Vinyl Background -->
        <img src="/images/piring-hitam.svg" alt="Vinyl"
            class="absolute -right-[35px] top-[10px] w-[80%] max-w-[130px] sm:max-w-[170px] md:max-w-[200px] z-0" />

        <!-- Album Cover Image -->
        <img :src="albumCover" :alt="title" class="w-full relative z-10" />

        <!-- Play Button -->
        <button class="absolute inset-0 flex items-center justify-center z-20 group/play">
          <div class="rounded-full p-3 group-hover/play:scale-110 transition-transform">
            <img src="/images/playbtn-white.svg" alt="Play" class="w-[50px] sm:w-[60px] md:w-[64px]" />
          </div>
        </button>

        <!-- Favorite Button -->
        <button class="absolute top-3 right-3 bg-white rounded-full p-2 z-20 hover:scale-110 transition-transform">
          <img src="/images/love.svg" alt="Love" class="w-[20px] h-[20px]" />
        </button>
      </div>

      <!-- Artist Info -->
      <div class="flex items-center gap-2 mb-1">
        <img :src="artistAvatar" :alt="artistName" class="w-5 h-5 rounded-full" />
        <span class="text-white font-medium text-[clamp(10px,0.8vw,12px)]">{{ artistName }}</span>
      </div>

      <!-- Title -->
      <h3 class="text-[clamp(16px,1.4vw,20px)] text-white font-bold text-gray-900 mb-2">{{ title }}</h3>

      <!-- Date and BPM -->
      <div class="flex justify-between items-center text-gray-600 mb-2">
        <div class="flex items-center gap-1">
          <img src="/images/date-gray.svg" alt="Calendar" class="w-[18px] h-[18px]">
          <span class="text-[clamp(10px,0.8vw,12px)] text-gray-400">{{ date }}</span>
        </div>
        <span class="text-gray-400 text-[clamp(10px,0.8vw,12px)]">{{ bpm }}</span>
      </div>

      <!-- Price -->
      <p class="text-[clamp(20px,2vw,28px)] font-bold text-white mb-3">{{ price }}</p>

      <!-- Stats -->
      <div class="flex items-center gap-4 mb-3">
        <div class="flex items-center gap-1">
          <img src="/images/unduh-white.svg" alt="Downloads" class="w-[16px] h-[16px]">
          <span class="text-gray-400 text-[clamp(10px,0.8vw,12px)]">{{ downloads }}</span>
        </div>
        <div class="flex items-center gap-1">
          <img src="/images/love-white.svg" alt="Likes" class="w-[16px] h-[16px]">
          <span class="text-gray-400 text-[clamp(10px,0.8vw,12px)]">{{ likes }}</span>
        </div>
        <div class="flex items-center gap-1">
          <img src="/images/rating-white.svg" alt="Rating" class="w-[16px] h-[16px]">
          <span class="text-gray-400 text-[clamp(10px,0.8vw,12px)]">{{ rating }}</span>
        </div>
      </div>

      <!-- Buttons -->
      <div class="flex gap-3">
        <button class="flex-1 text-white border-2 border-white font-bold py-2 text-[clamp(12px,1vw,14px)] hover:bg-white hover:text-black transition-colors">
          BUY NOW
        </button>
        <button class="border-2 border-white p-2 hover:bg-gray-200 transition-colors">
          <img src="/images/add-chart-white.svg" alt="add-chart" class="w-[20px] h-[20px]">
        </button>
      </div>

    </div>
  </div>
</template>




<script setup>
defineProps({
    albumCover: {
        type: String,
        required: true
    },
    artistAvatar: {
        type: String,
        required: true
    },
    artistName: {
        type: String,
        required: true
    },
    title: {
        type: String,
        required: true
    },
    date: {
        type: String,
        required: true
    },
    bpm: {
        type: String,
        required: true
    },
    price: {
        type: String,
        required: true
    },
    downloads: {
        type: [String, Number],
        required: true
    },
    likes: {
        type: [String, Number],
        required: true
    },
    rating: {
        type: [String, Number],
        required: true
    }
})
</script>

<style scoped>

</style>