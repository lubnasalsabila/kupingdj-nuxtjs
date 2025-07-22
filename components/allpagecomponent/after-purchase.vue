<template>
  <div class="relative pt-20 px-4 sm:px-6 md:px-10">
    <div class="flex flex-col md:flex-row">
      <!-- Judul -->
      <div class="md:basis-1/3 mb-6 md:mb-0">
        <h1 class="text-2xl sm:text-3xl md:text-4xl text-glancyr uppercase font-normal text-black mb-4 leading-snug">
          AFTER <br />
          PURCHASE,<br />
          YOU WILL GET
        </h1>

        <!-- Tombol swiper (hanya di mobile) -->
        <div class="flex gap-2 mt-2 md:hidden">
          <button
            @click="prevSlide"
            class="w-10 h-10 bg-black rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors"
          >
            <img src="/images/arrow-left.svg" alt="Previous" class="w-4 h-4" />
          </button>
          <button
            @click="nextSlide"
            class="w-10 h-10 bg-black rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors"
          >
            <img src="/images/arrow-right.svg" alt="Next" class="w-4 h-4" />
          </button>
        </div>
      </div>

      <!-- Purchase Cards -->
      <div class="md:basis-2/3 overflow-hidden relative">
        <!-- Wrapper -->
        <div
          ref="swiperContainer"
          class="flex transition-transform duration-300 ease-in-out"
          :style="`transform: translateX(-${currentSlide * slideWidth}px)`"
        >
          <div class="flex gap-4 sm:gap-6 min-w-max">
            <PurchaseCard
              purchase="/images/high-quality.svg"
              title="high-quality audio files (wav + mp3)"
              class="flex-shrink-0"
            />
            <PurchaseCard
              purchase="/images/license.svg"
              title="license certificate (pdf)"
              class="flex-shrink-0"
            />
            <PurchaseCard
              purchase="/images/download-access.svg"
              title="download access"
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

    const isMobile = window.innerWidth < 768
    const cardWidth = isMobile ? containerWidth : 300

    const visibleCards = Math.floor(containerWidth / cardWidth)
    slideWidth.value = cardWidth
    maxSlides.value = Math.max(0, 3 - visibleCards) // 3 cards total
  }
}

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % (maxSlides.value + 1)
}

const prevSlide = () => {
  currentSlide.value =
    currentSlide.value === 0 ? maxSlides.value : currentSlide.value - 1
}

onMounted(() => {
  calculateSlideWidth()
  window.addEventListener('resize', calculateSlideWidth)
})

onUnmounted(() => {
  window.removeEventListener('resize', calculateSlideWidth)
})
</script>
