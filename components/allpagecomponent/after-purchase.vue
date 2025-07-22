<template>
    <div class="relative pt-32 px-10">
        <!-- Title -->
         <div class="flex">
            <div class="basis-1/3">
                <h1 class="text-3xl text-glancyr uppercase font-normal text-black mb-8">AFTER <br> PURCHASE,<br>YOU WILL GET</h1>
            </div>
            <!-- Purchase Cards -->
            <div class="flex gap-2 min-w-max basis-2/3">
                <PurchaseCard 
                    purchase="/images/high-quality.svg"
                    title="high-quality audio files (wav + mp3)"
                />
                <PurchaseCard 
                    purchase="/images/license.svg"
                    title="license certificate (pdf)"
                />
                <PurchaseCard 
                    purchase="/images/download-access.svg"
                    title="download access"
                />
            </div>
         </div>
    </div>
</template>

<script setup>

</script>

<style scoped>

</style>