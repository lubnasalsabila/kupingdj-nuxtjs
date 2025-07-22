<template>
    <div class="relative pt-32 px-10">
        <!-- Title -->
         <div class="flex">
            <div class="basis-1/3">
                <h1 class="text-4xl font-bold text-black mb-8">EXPLORE OUR<br>ALBUM GENRE</h1>

                <!-- Navigation Arrows -->
                <div class="flex gap-2">
                    <button 
                        @click="prevSlide"
                        class="w-12 h-12 bg-black rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors"
                    >
                        <img src="/images/arrow-left.svg" alt="Previous" class="w-6 h-6" />
                    </button>
                    <button 
                        @click="nextSlide"
                        class="w-12 h-12 bg-black rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors"
                    >
                        <img src="/images/arrow-right.svg" alt="Next" class="w-6 h-6" />
                    </button>
                </div>
            </div>
             <!-- Swiper Container -->
            <div class="overflow-hidden relative  basis-2/3">
                <div 
                    ref="swiperContainer"
                    class="flex transition-transform duration-300 ease-in-out"
                    :style="`transform: translateX(-${currentSlide * slideWidth}px)`"
                >
                    <!-- Genre Cards -->
                    <div class="flex gap-6 min-w-max">
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
const slideWidth = ref(300) // Default width, will be calculated
const maxSlides = ref(0)

const calculateSlideWidth = () => {
    if (swiperContainer.value) {
        const containerWidth = swiperContainer.value.parentElement.clientWidth
        const cardWidth = 250 // Approximate width of each card + gap
        const visibleCards = Math.floor(containerWidth / cardWidth)
        slideWidth.value = cardWidth
        maxSlides.value = Math.max(0, 6 - visibleCards) // 6 total cards minus visible cards
    }
}

const nextSlide = () => {
    if (currentSlide.value < maxSlides.value) {
        currentSlide.value++
    } else {
        currentSlide.value = 0 // Loop back to start
    }
}

const prevSlide = () => {
    if (currentSlide.value > 0) {
        currentSlide.value--
    } else {
        currentSlide.value = maxSlides.value // Loop to end
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

<style scoped>

</style>