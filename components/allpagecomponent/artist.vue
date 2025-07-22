<template>
  <div class="min-h-screen bg-gray-50 py-10 overflow-hidden">
    <!-- Header section -->
    <div class="container mx-auto px-10 mb-12 flex justify-between items-center">
      <h1 class="text-4xl font-bold text-black">THE ARTIST</h1>
      <p class="text-gray-700 max-w-md text-start">
        Meet the talented artists featured on Kuping DJ! Discover their latest mixtapes and albums, and immerse yourself in their creative journeys.
      </p>
    </div>

    <!-- Swiper carousel -->
    <div class="relative">
      <swiper
        :modules="[Navigation]"
        :slides-per-view="4.5"
        :space-between="20"
        :loop="true"
        :navigation="{
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }"
        @slideChange="onSlideChange"
        class="artist-swiper"
      >
        <swiper-slide v-for="(artist, index) in artists" :key="index">
          <div :class="{ 'grayscale': currentSlide !== index }">
            <ArtistBingkai 
              :image="artist.image" 
              :name="artist.name"
            />
          </div>
        </swiper-slide>
      </swiper>

      <!-- Navigation arrows -->
      <div class="swiper-button-prev absolute left-4 top-1/2 -translate-y-1/2 z-10 bg-gray-500 bg-opacity-50 rounded-full w-12 h-12 flex items-center justify-center text-white">
        <img src="/images/arrow-left.svg" alt="prev" class="w-6 h-6">
      </div>
      <div class="swiper-button-next absolute right-0 top-1/2 -translate-y-1/2 z-10 bg-gray-500 bg-opacity-50 rounded-full w-12 h-12 flex items-center justify-center text-white">
        <img src="/images/arrow-right.svg" alt="next" class="w-6 h-6">
      </div>
    </div>

    <!-- Explore button -->
    <div class="container mx-auto px-4 mt-12 flex justify-center">
      <button
        @click="showModal = true"
        class="flex items-center text-white font-semibold uppercase transition-colors"
      >
        <span class="bg-[#A10501] px-6 py-4 text-base">EXPLORE ALL ARTIST</span>
        <span class="bg-black px-4 py-4 flex items-center justify-center">
          <img src="/images/arrow-white.svg" alt="arrow" class="w-6 h-6" />
        </span>
      </button>
    </div>

    <!-- Modal -->
    <div v-if="showModal" class="fixed inset-0 bg-black bg-opacity-50 z-50 flex items-center justify-center p-4">
      <div class="bg-white rounded-lg max-w-6xl max-h-[90vh] overflow-auto p-8">
        <div class="flex justify-between items-center mb-6">
          <h2 class="text-3xl font-bold">All Artists</h2>
          <button 
            @click="showModal = false"
            class="text-gray-500 hover:text-gray-700"
          >
            <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
        
        <div class="grid grid-cols-4 gap-6">
          <ArtistBingkai 
            v-for="(artist, index) in allArtists" 
            :key="index"
            :image="artist.image" 
            :name="artist.name"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation } from 'swiper/modules'
import ArtistBingkai from '../artist/bingkai.vue'

// Import Swiper styles
import 'swiper/css'
import 'swiper/css/navigation'

const currentSlide = ref(0)
const showModal = ref(false)

const artists = [
  { name: 'WISHNU SANTIKA', image: '/images/whisnu2.jpeg' },
  { name: 'EKA GUSTIWANA', image: '/images/eka.jpeg' },
  { name: 'WEIRD GENIUS', image: '/images/weird.jpeg' },
  { name: 'DIPHA BARUS', image: '/images/dipha.jpeg' },
  { name: 'MIDNIGHT QUICKIE', image: '/images/midnight.jpeg' },
  { name: 'RAISA', image: '/images/raisa.jpeg' },
  { name: 'TULUS', image: '/images/tulus.jpeg' },
  { name: 'AFGAN', image: '/images/Afgan.jpeg' }
]

const allArtists = [
  ...artists,
  { name: 'NOAH', image: '/images/whisnu2.jpeg' },
  { name: 'PETERPAN', image: '/images/whisnu2.jpeg' },
  { name: 'SHEILA ON 7', image: '/images/whisnu2.jpeg' },
  { name: 'DEWA 19', image: '/images/whisnu2.jpeg' },
  { name: 'GIGI', image: '/images/whisnu2.jpeg' },
  { name: 'SLANK', image: '/images/whisnu2.jpeg' },
  { name: 'UNGU', image: '/images/whisnu2.jpeg' },
  { name: 'PADI', image: '/images/whisnu2.jpeg' }
]

const onSlideChange = (swiper) => {
  currentSlide.value = swiper.realIndex
}
</script>

<style scoped>
.grayscale {
  filter: grayscale(100%);
  transition: filter 0.3s ease;
}

:deep(.swiper-wrapper) {
    margin-left: -20px;
}
.artist-swiper {
  padding: 0 60px;
}

:deep(.swiper-button-prev),
:deep(.swiper-button-next) {
  color: white;
  width: 48px;
  height: 48px;
}

:deep(.swiper-button-prev:after),
:deep(.swiper-button-next:after) {
  display: none;
}
</style>
