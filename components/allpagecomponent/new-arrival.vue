<template>
  <div class="min-h-screen bg-gray-50 py-16 overflow-hidden">
    <!-- Header section -->
    <div class="container px-10 mb-12 flex justify-between items-center">
      <h1 class="text-4xl text-glancyr uppercase font-normal text-black">NEW ARRIVAL MIXTAPE</h1>
      
      <!-- Navigation arrows in header -->
      <div class="flex gap-2">
        <!-- Prev Button -->
        <div class="swiper-button-prev-custom cursor-pointer bg-black rounded-full w-12 h-12 flex items-center justify-center shrink-0">
            <img src="/images/arrow-left.svg" alt="previous" class="w-5 h-5" />
        </div>
        
        <!-- Next Button -->
        <div class="swiper-button-next-custom cursor-pointer bg-black rounded-full w-12 h-12 flex items-center justify-center">
            <img src="/images/arrow-right.svg" alt="next" class="w-5 h-5" />
        </div>
      </div>
    </div>

    <!-- Swiper carousel -->
    <div class="relative ps-5">
      <swiper
        :modules="[Navigation]"
        :slides-per-view="4"
        :space-between="30"
        :loop="false"
        :navigation="{
          nextEl: '.swiper-button-next-custom',
          prevEl: '.swiper-button-prev-custom'
        }"
        class="mixtape-swiper px-16"
      >
        <swiper-slide v-for="(mixtape, index) in mixtapes" :key="index">
          <MusicCardVinyl 
            :album-cover="mixtape.albumCover"
            :artist-avatar="mixtape.artistAvatar"
            :artist-name="mixtape.artistName"
            :title="mixtape.title"
            :date="mixtape.date"
            :bpm="mixtape.bpm"
            :price="mixtape.price"
            :downloads="mixtape.downloads"
            :likes="mixtape.likes"
            :rating="mixtape.rating"
          />
        </swiper-slide>
      </swiper>
    </div>

    <!-- Explore button -->
    <div class="container mx-auto px-4 mt-12 flex justify-center">
      <button
        @click="showModal = true"
        class="flex items-center text-white font-semibold uppercase transition-colors"
      >
        <span class="bg-[#A10501] px-6 py-4 text-base">EXPLORE ALL MIX TAPE</span>
        <span class="bg-black px-4 py-4 flex items-center justify-center">
          <img src="/images/arrow-white.svg" alt="arrow" class="w-6 h-6" />
        </span>
      </button>
    </div>

    <!-- Modal -->
    <div v-if="showModal" class="fixed inset-0 bg-black bg-opacity-50 z-50 flex items-center justify-center p-4">
      <div class="bg-white rounded-lg max-w-7xl max-h-[90vh] overflow-auto p-8">
        <div class="flex justify-between items-center mb-6">
          <h2 class="text-3xl font-bold">All Mixtapes</h2>
          <button 
            @click="showModal = false"
            class="text-gray-500 hover:text-gray-700"
          >
            <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
        
        <div class="grid grid-cols-3 gap-6">
          <MusicCardVinyl 
            v-for="(mixtape, index) in allMixtapes" 
            :key="index"
            :album-cover="mixtape.albumCover"
            :artist-avatar="mixtape.artistAvatar"
            :artist-name="mixtape.artistName"
            :title="mixtape.title"
            :date="mixtape.date"
            :bpm="mixtape.bpm"
            :price="mixtape.price"
            :downloads="mixtape.downloads"
            :likes="mixtape.likes"
            :rating="mixtape.rating"
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
import MusicCardVinyl from '../music/card-vinyl.vue'

// Import Swiper styles
import 'swiper/css'
import 'swiper/css/navigation'

const showModal = ref(false)

const mixtapes = [
  {
    albumCover: '/images/music/cartel.jpg',
    artistAvatar: '/images/whisnu.jpeg',
    artistName: 'Whisnu Santika',
    title: 'Cartel Mixtape Exclusive On Kuping DJ',
    date: '02 July, 2025',
    bpm: '150BPM',
    price: 'Rp. 200,000',
    downloads: '123',
    likes: '100',
    rating: '4.5'
  },
  {
    albumCover: '/images/music/sweet-scar.jpg',
    artistAvatar: '/images/eka.jpeg',
    artistName: 'Eka Gustiwana',
    title: 'Sweet Scars Mixtape Exclusive On Kuping DJ',
    date: '02 July, 2025',
    bpm: '160BPM',
    price: 'Rp. 300,000',
    downloads: '123',
    likes: '100',
    rating: '4.5'
  },
  {
    albumCover: '/images/music/catalyst.jpg',
    artistAvatar: '/images/weird.jpeg',
    artistName: 'Weird Genius',
    title: 'Catalyst Mixtape Exclusive On Kuping DJ',
    date: '02 July, 2025',
    bpm: '150BPM',
    price: 'Rp. 350,000',
    downloads: '123',
    likes: '100',
    rating: '4.5'
  },
  {
    albumCover: '/images/music/Hush.jpg',
    artistAvatar: '/images/whisnu.jpeg',
    artistName: 'Weird Genius',
    title: 'HUSH Mixtape Exclusive On Kuping DJ',
    date: '02 July, 2025',
    bpm: '150BPM',
    price: 'Rp. 200,000',
    downloads: '123',
    likes: '100',
    rating: '4.5'
  },
  {
    albumCover: '/images/music/noone.jpg',
    artistAvatar: '/images/whisnu.jpeg',
    artistName: 'Whisnu Santika',
    title: 'Another Mixtape Exclusive On Kuping DJ',
    date: '03 July, 2025',
    bpm: '140BPM',
    price: 'Rp. 250,000',
    downloads: '89',
    likes: '75',
    rating: '4.2'
  }
]

const allMixtapes = [
  ...mixtapes,
  {
    albumCover: '/images/cartel.jpeg',
    artistAvatar: '/images/whisnu.jpeg',
    artistName: 'DJ Remix',
    title: 'Beat Drop Mixtape Exclusive On Kuping DJ',
    date: '04 July, 2025',
    bpm: '128BPM',
    price: 'Rp. 180,000',
    downloads: '156',
    likes: '120',
    rating: '4.7'
  },
  {
    albumCover: '/images/cartel.jpeg',
    artistAvatar: '/images/whisnu.jpeg',
    artistName: 'Sound Master',
    title: 'Electronic Vibes Mixtape Exclusive On Kuping DJ',
    date: '05 July, 2025',
    bpm: '135BPM',
    price: 'Rp. 220,000',
    downloads: '97',
    likes: '85',
    rating: '4.3'
  },
  {
    albumCover: '/images/cartel.jpeg',
    artistAvatar: '/images/whisnu.jpeg',
    artistName: 'Bass Master',
    title: 'Deep House Mixtape Exclusive On Kuping DJ',
    date: '06 July, 2025',
    bpm: '120BPM',
    price: 'Rp. 280,000',
    downloads: '201',
    likes: '180',
    rating: '4.8'
  }
]
</script>

<style scoped>
.mixtape-swiper {
  overflow: visible;
}

:deep(.swiper-button-next-custom),
:deep(.swiper-button-prev-custom) {
  position: static;
  margin: 0;
}

:deep(.swiper-button-next-custom:after),
:deep(.swiper-button-prev-custom:after) {
  display: none;
}
</style>