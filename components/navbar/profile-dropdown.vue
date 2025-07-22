<template>
  <div class="relative" ref="dropdownContainer">
    <div class="flex items-center">
      <img src="/images/avatar.svg" alt="Avatar" class="w-8 h-8 transition-transform duration-300 ease-in-out hover:scale-[1.2]">
      <button @click="toggleDropdown" class="ml-2">
        <img src="/images/down-arrow.svg" alt="Down Arrow" class="w-4 h-4">
      </button>
    </div>
    
    <div v-if="isDropdownOpen" class="absolute left-0 top-full mt-2 z-10">
      <button 
        @click="logout"
        class="bg-[#A10501] text-white px-4 py-2 rounded-[10px] whitespace-nowrap hover:bg-[#8a0401] transition-colors"
      >
        Logout
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isDropdownOpen = ref(false)
const dropdownContainer = ref(null)

const toggleDropdown = () => {
  isDropdownOpen.value = !isDropdownOpen.value
}

const logout = () => {
  console.log('Logout clicked')
  isDropdownOpen.value = false
}

const closeDropdown = (event) => {
  if (dropdownContainer.value && !dropdownContainer.value.contains(event.target)) {
    isDropdownOpen.value = false
  }
}

onMounted(() => {
  document.addEventListener('click', closeDropdown)
})

onUnmounted(() => {
  document.removeEventListener('click', closeDropdown)
})
</script>

<style scoped>

</style>