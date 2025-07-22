<template>
    <div class="relative overflow-hidden max-w-[290px] max-h-[330px]">
        <!-- Image container -->
        <div class="relative">
            <img 
                :src="image" 
                :alt="name"
                class="w-[290px] h-[330px] object-cover"
            >
            <!-- Gradient overlay with customizable color -->
            <div 
                class="absolute inset-0"
                style=" background: linear-gradient(to bottom, transparent 50%, rgba(161, 5, 1, 0.8) 100%)"
            ></div>
        </div>
        
        <!-- Artist name -->
        <div class="absolute bottom-4 left-4">
            <h3 class="text-white text-2xl font-bold uppercase italic">
                {{ name }}
            </h3>
        </div>
    </div>
</template>

<script setup>
defineProps({
    image: {
        type: String,
        required: true
    },
    name: {
        type: String,
        required: true
    }
})
</script>

<style lang="scss" scoped>

</style>