<template>
        <!-- Main card content -->
        <div class="relative z-10 max-w-[270px]">
            <!-- Album Cover with Play Button and Love Icon -->
            <div class="relative mb-4">
                <img 
                    :src="albumCover" 
                    :alt="title"
                    class="w-full"
                >
                <!-- Love Button -->
                <button class="absolute top-4 right-4 bg-white rounded-full p-3 hover:scale-110 transition-transform">
                    <img src="/images/love.svg" alt="Love" class="w-6 h-6">
                </button>
            </div>

            <!-- Title -->
            <h3 class="text-xl font-bold text-gray-900 mb-2 text-geist">{{ title }}</h3>

            <!-- Date and BPM -->
            <div class="flex items-center text-xs text-gray-600 mb-2">
                <img src="/images/calendar.svg" alt="Calendar" class="w-5 h-5">
                <span>{{ date }}</span>
            </div>

            <!-- Price -->
            <p class="text-lg font-bold text-gray-900 mb-4 text-geist">{{ price }}</p>

            <!-- Buttons -->
            <div class="flex gap-3">
                <button class="flex-1 bg-white border-2 border-[#A10501] text-[#A10501] font-bold py-3 px-6 hover:bg-[#A10501] hover:text-white transition-colors">
                    BUY BUNDLING
                </button>
                <button class="bg-white border-2 border-black p-3 hover:bg-gray-200 transition-colors">
                    <img src="/images/add-chart-black.svg" alt="add-chart" class="w-6 h-6">
                </button>
            </div>

        </div>
</template>

<script setup>
defineProps({
    albumCover: {
        type: String,
        required: true
    },
    title: {
        type: String,
        required: true
    },
    date: {
        type: String,
        required: true
    },
    price: {
        type: String,
        required: true
    }
})
</script>

<style scoped>

</style>