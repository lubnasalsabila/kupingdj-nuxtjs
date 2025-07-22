<template>
    <div class="text-center">
        <div class="text-6xl font-light text-black mb-2 text-glancyr">{{ displayNumber }}</div>
        <div class="text-lg text-gray-700">Best Artist</div>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const targetNumber = 70
const displayNumber = ref(0)
const duration = 1500 // 2 seconds animation

onMounted(() => {
  const startTime = performance.now()
  
  const animate = (currentTime) => {
    const elapsed = currentTime - startTime
    const progress = Math.min(elapsed / duration, 1)
    
    // Easing function for smooth animation
    const easeOutQuart = 1 - Math.pow(1 - progress, 4)
    
    displayNumber.value = Math.floor(easeOutQuart * targetNumber)
    
    if (progress < 1) {
      requestAnimationFrame(animate)
    } else {
      displayNumber.value = targetNumber
    }
  }
  
  requestAnimationFrame(animate)
})
</script>

<style lang="scss" scoped>

</style>