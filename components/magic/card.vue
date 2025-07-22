<template>
  <div
    :class="[
      'relative w-[470px] h-[253px] border border-gray-300 overflow-hidden cursor-pointer transition-transform duration-300 hover:-translate-y-1',
      isTailwindColor ? `bg-${color}` : '',
      textcolor
    ]"
    :style="!isTailwindColor ? { backgroundColor: color } : {}"
    style="background-image: url('/images/back-card-themagic.svg'); background-size: cover; background-position: center; background-repeat: no-repeat;"
  >
    <!-- Text content -->
    <div class="absolute top-6 left-6 z-20 w-[250px]">
      <h2 class="text-2xl font-bold leading-tight tracking-wide uppercase">
        {{ title }}
      </h2>
    </div>

    <!-- Preview image -->
    <div class="absolute bottom-0 right-0 z-10">
      <img 
        :src="image" 
        alt="Album Preview"
        class="h-full object-contain"
      />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  image: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  color: {
    type: String,
    required: true
  },
  textcolor: {
    type: String,
    required: true
  }
})

// Cek apakah props color adalah class tailwind seperti "white", "red-500", dll
const isTailwindColor = ['white', 'red-500', 'blue-300', 'black', 'gray-100'].includes(props.color)
</script>
