<template>
  <div
    class="flex overflow-hidden shadow-lg w-[602px]"
    :style="{ height: cardHeight }"
  >
    <!-- Left section with image -->
    <div class="relative w-1/2 bg-gray-200">
      <div class="relative w-full h-full">
        <img 
          :src="personImage" 
          :alt="personName"
          class="absolute inset-0 w-full h-full object-cover"
        />
        <!-- Gradient overlay -->
        <div 
          class="absolute inset-0"
          style="background: linear-gradient(to bottom, rgba(0,0,0,0) 50%, rgba(0,0,0,0.7) 100%)"
        ></div>
      </div>

      <!-- Name and title overlay -->
      <div class="absolute bottom-4 left-4 text-white">
        <h3 class="font-normal text-4xl leading-tight text-glancyr uppercase italic">{{ personName }}</h3>
        <p class="text-2xl text-glancyr uppercase font-normal italic">{{ personTitle }}</p>
      </div>
    </div>

    <!-- Right section with quote -->
    <div class="relative w-1/2 bg-[#A10501] p-6 flex flex-col justify-end h-full">
      <!-- Quote icon -->
      <img 
        src="/images/kutip2.svg" 
        alt="quote"
        class="absolute top-6 w-24 h-24"
      />
      
      <!-- Quote text -->
      <p
        class="text-white leading-relaxed text-geist mr-4"
        :class="quoteTextSize"
      >
        {{ quoteText }}
      </p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  personImage: {
    type: String,
    required: true
  },
  personName: {
    type: String,
    required: true
  },
  personTitle: {
    type: String,
    required: true
  },
  quoteText: {
    type: String,
    required: true
  },
  cardHeight: {
    type: String,
    default: '332px' // contoh default tinggi
  },
  quoteTextSize: {
    type: String,
    default: 'text-2xl' // contoh default ukuran text
  }
})
</script>
