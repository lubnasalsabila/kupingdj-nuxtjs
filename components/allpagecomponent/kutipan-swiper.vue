<template>
  <div class="relative py-16 ps-10">
    <!-- Header Section -->
    <div class="flex flex-row justify-between items-start mb-12">
      <div class="flex-1 basis-2/3">
        <h1 class="text-4xl text-glancyr uppercase font-normal text-black leading-tight">
          WHAT PEOPLE SAID<br />
          ABOUT KUPING DJ
        </h1>
      </div>
      <div class="flex-1 max-w-md ml-32 basis-1/3 me-10">
        <p class="text-gray-600 text-sm leading-relaxed">
          Discover what our users are saying about Kuping DJ!
          From seamless music discovery to an extensive library of
          mixtapes and albums.
        </p>
      </div>
    </div>

    <!-- Swiper Container -->
    <div class="relative">
      <!-- Swiper carousel -->
      <Swiper
        :modules="[Navigation]"
        :slides-per-view="2"
        :space-between="20"
        :loop="true"
        :navigation="{
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }"
        @slideChange="onSlideChange"
        class="quote-swiper"
      >
        <SwiperSlide v-for="(quote, index) in quotes" :key="index">
            <KutipanCard
              :personImage="quote.image"
              :personName="quote.name"
              :personTitle="quote.title"
              :quoteText="quote.text"
              :cardHeight="quote.height"
              :quoteTextSize="quote.textsize"
            />
        </SwiperSlide>
      </Swiper>

      <!-- Navigation Arrows -->
      <div
        class="swiper-button-prev absolute left-0 top-1/2 -translate-y-1/2 z-10 w-12 h-12 bg-gray-500 bg-opacity-50 rounded-full flex items-center justify-center shadow-lg hover:shadow-xl transition-shadow"
      >
        <img src="/images/arrow-left.svg" alt="Previous" class="w-6 h-6" />
      </div>
      <div
        class="swiper-button-next absolute right-0 top-1/2 -translate-y-1/2 z-10 w-12 h-12 bg-gray-500 bg-opacity-50 rounded-full flex items-center justify-center shadow-lg hover:shadow-xl transition-shadow"
      >
        <img src="/images/arrow-right.svg" alt="Next" class="w-6 h-6" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation } from 'swiper/modules'
import KutipanCard from '../kutipan/card.vue'

// Import Swiper styles
import 'swiper/css'
import 'swiper/css/navigation'

const currentSlide = ref(0)

const quotes = [
    {
    image: "/images/adhitama.svg",
    name: "ADHITAMA ADIARJA",
    title: "DJ OXQ",
    text: "Kuping DJ adalah platform yang luar biasa! Saya menemukan banyak mixtape dan album yang sesuai dengan selera saya. Setiap kali saya mencari musik baru, saya selalu kembali ke sini. Terima kasih, Kuping DJ!",
    height: "450px",
    textsize: "text-xl"
    },
    {
    image: "/images/bagas.svg",
    name: "BAGAS WIRANTO",
    title: "DJ BAYKILLA",
    text: "Sebagai DJ, saya sangat menghargai koleksi mixtape dan album yang ada di Kuping DJ. Ini adalah sumber inspirasi yang tak ternilai untuk set saya. Sangat direkomendasikan!",
    height: "450px",
    textsize: "text-xl"
    },
    {
    image: "/images/yudyy.jpg",
    name: "YOUDY YANSYAH",
    title: "DJ OXO",
    text: "Kuping DJ adalah platform yang luar biasa! Saya menemukan banyak mixtape dan album yang sesuai dengan selera saya. Setiap kali saya mencari musik baru, saya selalu kembali ke sini. Terima kasih, Kuping DJ!",
    height: "450px",
    textsize: "text-xl"
    }
    
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
