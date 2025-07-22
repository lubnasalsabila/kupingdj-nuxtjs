<template>
    <div class="bg-[#F7F7F7] pt-14">
        <!-- Header with title and filter buttons -->
        <div class="flex justify-between items-center mb-8 px-10">
            <h1 class="text-4xl text-glancyr uppercase font-normal text-black">MOST POPULAR MIXTAPE</h1>
            <div class="flex">
                <button 
                    @click="activeFilter = 'topPurchased'"
                    :class="[
                        'px-4 py-2 text-sm font-medium border transition-colors',
                        activeFilter === 'topPurchased' 
                            ? 'bg-black text-white border-black' 
                            : 'bg-white text-black border-gray-300 hover:border-gray-400'
                    ]"
                >
                    TOP PURCHASED
                </button>
                <button 
                    @click="activeFilter = 'highestRated1'"
                    :class="[
                        'px-4 py-2 text-sm font-medium border transition-colors',
                        activeFilter === 'highestRated1' 
                            ? 'bg-black text-white border-black' 
                            : 'bg-white text-black border-gray-300 hover:border-gray-400'
                    ]"
                >
                    HIGHEST RATED
                </button>
                <button 
                    @click="activeFilter = 'highestRated2'"
                    :class="[
                        'px-4 py-2 text-sm font-medium border transition-colors',
                        activeFilter === 'highestRated2' 
                            ? 'bg-black text-white border-black' 
                            : 'bg-white text-black border-gray-300 hover:border-gray-400'
                    ]"
                >
                    HIGHEST RATED
                </button>
            </div>
        </div>

        <!-- Music cards grid -->
        <div class="grid grid-cols-5 gap-2 px-2">
            <div v-for="item in currentItems" :key="item.id" class="">
                <MusicCardVinyl 
                    :album-cover="item.albumCover"
                    :artist-avatar="item.artistAvatar"
                    :artist-name="item.artistName"
                    :title="item.title"
                    :date="item.date"
                    :bpm="item.bpm"
                    :price="item.price"
                    :downloads="item.downloads"
                    :likes="item.likes"
                    :rating="item.rating"
                    class="h-full"
                />
            </div>
            
        </div>
    </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const activeFilter = ref('topPurchased')

const topPurchasedItems = [
    {
        id: 1,
        albumCover: "/images/music/cartel.jpg",
        artistAvatar: "/images/whisnu.jpeg",
        artistName: "Whisnu Santika",
        title: "Cartel Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 2,
        albumCover: "/images/music/all-good.jpg",
        artistAvatar: "/images/dipha.jpeg",
        artistName: "Dipha Barus",
        title: "All Good Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 3,
        albumCover: "/images/music/noone.jpg",
        artistAvatar: "/images/dipha.jpeg",
        artistName: "Dipha Barus",
        title: "No One Can Stop Us Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 4,
        albumCover: "/images/music/Hush.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "HUSH Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 5,
        albumCover: "/images/music/lathi.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Lathi Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 6,
        albumCover: "/images/music/tequila.jpg",
        artistAvatar: "/images/whisnu.jpeg",
        artistName: "Whisnu Santika",
        title: "Tequila Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 7,
        albumCover: "/images/music/Sahara.jpg",
        artistAvatar: "/images/whisnu.jpeg",
        artistName: "Whisnu Santika",
        title: "Sahara Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 8,
        albumCover: "/images/music/lunatic.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Lunatic Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 9,
        albumCover: "/images/music/tersimpan.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Tersimpan Di Hati Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 10,
        albumCover: "/images/music/catalyst.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Catlyst Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    }
]

const highestRated1Items = [
    {
        id: 11,
        albumCover: "/images/music/lathi.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Lathi Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 12,
        albumCover: "/images/music/Hush.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "HUSH Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 13,
        albumCover: "/images/music/cartel.jpg",
        artistAvatar: "/images/whisnu.jpeg",
        artistName: "Whisnu Santika",
        title: "Cartel Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 14,
        albumCover: "/images/music/all-good.jpg",
        artistAvatar: "/images/dipha.jpeg",
        artistName: "Dipha Barus",
        title: "All Good Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 15,
        albumCover: "/images/music/noone.jpg",
        artistAvatar: "/images/dipha.jpeg",
        artistName: "Dipha Barus",
        title: "No One Can Stop Us Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 16,
        albumCover: "/images/music/tequila.jpg",
        artistAvatar: "/images/whisnu.jpeg",
        artistName: "Whisnu Santika",
        title: "Tequila Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 17,
        albumCover: "/images/music/Sahara.jpg",
        artistAvatar: "/images/whisnu.jpeg",
        artistName: "Whisnu Santika",
        title: "Sahara Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 18,
        albumCover: "/images/music/lunatic.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Lunatic Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 19,
        albumCover: "/images/music/tersimpan.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Tersimpan Di Hati Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 20,
        albumCover: "/images/music/catalyst.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Catlyst Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    }
]

const highestRated2Items = [
    {
        id: 21,
        albumCover: "/images/music/Sahara.jpg",
        artistAvatar: "/images/whisnu.jpeg",
        artistName: "Whisnu Santika",
        title: "Sahara Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 22,
        albumCover: "/images/music/catalyst.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Catlyst Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 23,
        albumCover: "/images/music/tersimpan.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Tersimpan Di Hati Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 24,
        albumCover: "/images/music/tequila.jpg",
        artistAvatar: "/images/whisnu.jpeg",
        artistName: "Whisnu Santika",
        title: "Tequila Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 25,
        albumCover: "/images/music/lunatic.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Lunatic Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 26,
        albumCover: "/images/music/cartel.jpg",
        artistAvatar: "/images/whisnu.jpeg",
        artistName: "Whisnu Santika",
        title: "Cartel Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 27,
        albumCover: "/images/music/all-good.jpg",
        artistAvatar: "/images/dipha.jpeg",
        artistName: "Dipha Barus",
        title: "All Good Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 28,
        albumCover: "/images/music/noone.jpg",
        artistAvatar: "/images/dipha.jpeg",
        artistName: "Dipha Barus",
        title: "No One Can Stop Us Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 29,
        albumCover: "/images/music/Hush.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "HUSH Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    },
    {
        id: 30,
        albumCover: "/images/music/lathi.jpg",
        artistAvatar: "/images/weird.jpeg",
        artistName: "Weird Genius",
        title: "Lathi Mixtape Exclusive On Kuping DJ",
        date: "02 July, 2025",
        bpm: "150BPM",
        price: "Rp. 200,000",
        downloads: "123",
        likes: "100",
        rating: "4.5"
    }
]

const currentItems = computed(() => {
    switch (activeFilter.value) {
        case 'topPurchased':
            return topPurchasedItems
        case 'highestRated1':
            return highestRated1Items
        case 'highestRated2':
            return highestRated2Items
        default:
            return topPurchasedItems
    }
})
</script>

<style lang="scss" scoped>

</style>