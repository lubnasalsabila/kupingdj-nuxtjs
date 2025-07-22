<template>
    <div class="overflow-hidden bg-[#A10501] py-3">
        <div class="marquee">
            <div class="marquee-content">
                <span class="text-white text-3xl font-medium uppercase tracking-wider mx-4">
                    DISCOVER THE ULTIMATE EXPERIENCE
                </span>
                <span class="text-white text-3xl mx-4">•</span>
                <span class="text-white text-3xl font-medium uppercase tracking-wider mx-4">
                    DISCOVER THE ULTIMATE EXPERIENCE
                </span>
                <span class="text-white text-3xl mx-4">•</span>
                <span class="text-white text-3xl font-medium uppercase tracking-wider mx-4">
                    DISCOVER THE ULTIMATE EXPERIENCE
                </span>
                <span class="text-white text-3xl mx-4">•</span>
                <span class="text-white text-3xl font-medium uppercase tracking-wider mx-4">
                    DISCOVER THE ULTIMATE EXPERIENCE
                </span>
                <span class="text-white text-3xl mx-4">•</span>
            </div>
            <div class="marquee-content" aria-hidden="true">
                <span class="text-white text-3xl font-medium uppercase tracking-wider mx-4">
                    DISCOVER THE ULTIMATE EXPERIENCE
                </span>
                <span class="text-white text-3xl mx-4">•</span>
                <span class="text-white text-3xl font-medium uppercase tracking-wider mx-4">
                    DISCOVER THE ULTIMATE EXPERIENCE
                </span>
                <span class="text-white text-3xl mx-4">•</span>
                <span class="text-white text-3xl font-medium uppercase tracking-wider mx-4">
                    DISCOVER THE ULTIMATE EXPERIENCE
                </span>
                <span class="text-white text-3xl mx-4">•</span>
                <span class="text-white text-3xl font-medium uppercase tracking-wider mx-4">
                    DISCOVER THE ULTIMATE EXPERIENCE
                </span>
                <span class="text-white text-3xl mx-4">•</span>
            </div>
        </div>
    </div>
</template>

<script setup>

</script>

<style scoped>
.marquee {
    display: flex;
    overflow: hidden;
    user-select: none;
    gap: 0;
}

.marquee-content {
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: space-around;
    min-width: 100%;
    animation: scroll 30s linear infinite;
}

@keyframes scroll {
    from {
        transform: translateX(0);
    }
    to {
        transform: translateX(-100%);
    }
}
</style>