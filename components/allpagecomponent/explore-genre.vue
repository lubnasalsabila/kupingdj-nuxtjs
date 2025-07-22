<template>
  <div class="relative pt-20 px-4 sm:px-6 md:px-10">
    <!-- Title dan navigasi -->
    <div class="flex flex-col md:flex-row">
      <!-- Kiri -->
      <div class="md:basis-1/3 mb-6 md:mb-0">
        <h1 class="text-2xl sm:text-3xl md:text-4xl text-glancyr uppercase font-normal text-black mb-6 sm:mb-8">
          EXPLORE OUR<br />ALBUM GENRE
        </h1>

        <!-- Tombol navigasi -->
        <div class="flex gap-2">
          <button
            @click="prevSlide"
            class="w-10 h-10 sm:w-12 sm:h-12 bg-black rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors"
          >
            <img src="/images/arrow-left.svg" alt="Previous" class="w-4 h-4 sm:w-6 sm:h-6" />
          </button>
          <button
            @click="nextSlide"
            class="w-10 h-10 sm:w-12 sm:h-12 bg-black rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors"
          >
            <img src="/images/arrow-right.svg" alt="Next" class="w-4 h-4 sm:w-6 sm:h-6" />
          </button>
        </div>
      </div>

      <!-- Kanan (Swiper Container) -->
      <div class="overflow-hidden relative md:basis-2/3">
        <div
          ref="swiperContainer"
          class="flex transition-transform duration-300 ease-in-out"
          :style="`transform: translateX(-${currentSlide * slideWidth}px)`"
        >
          <div class="flex gap-4 sm:gap-6 min-w-max">
            <!-- Genre Cards -->
            <GenreCard
              genre="/images/edm.svg"
              genrename="EDM"
              class="flex-shrink-0"
            />
            <GenreCard
              genre="/images/hiphop.svg"
              genrename="HIP-HOP"
              class="flex-shrink-0"
            />
            <GenreCard
              genre="/images/RandB.svg"
              genrename="R&B"
              class="flex-shrink-0"
            />
            <GenreCard
              genre="/images/pop.svg"
              genrename="POP"
              class="flex-shrink-0"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const swiperContainer = ref(null)
const currentSlide = ref(0)
const slideWidth = ref(300)
const maxSlides = ref(0)

const calculateSlideWidth = () => {
  if (swiperContainer.value) {
    const containerWidth = swiperContainer.value.parentElement.clientWidth

    let cardWidth = 250
    if (window.innerWidth < 640) {
      cardWidth = containerWidth // Tampilkan 1 card penuh saat mobile
    }

    const visibleCards = Math.floor(containerWidth / cardWidth)
    slideWidth.value = cardWidth
    maxSlides.value = Math.max(0, 4 - visibleCards) // 4 card total
  }
}

const nextSlide = () => {
  if (currentSlide.value < maxSlides.value) {
    currentSlide.value++
  } else {
    currentSlide.value = 0
  }
}

const prevSlide = () => {
  if (currentSlide.value > 0) {
    currentSlide.value--
  } else {
    currentSlide.value = maxSlides.value
  }
}

onMounted(() => {
  calculateSlideWidth()
  window.addEventListener('resize', calculateSlideWidth)
})

onUnmounted(() => {
  window.removeEventListener('resize', calculateSlideWidth)
})
</script>
