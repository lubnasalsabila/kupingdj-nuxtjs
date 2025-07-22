<template>
    <div class="relative min-h-screen pt-16">
        <!-- Mixtape Section -->
        <section class="relative bg-black">
             <!-- Background Image Layer -->
            <div class="absolute inset-0 z-10 pointer-events-none">
                <img src="/public/images/back-left-kupingdj.svg" alt="bg" class="w-[887px] h-[568px] object-cover" />
            </div>
            <!-- Content-top -->
            <div class="absolute z-10 container mx-auto px-10 ">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-start pt-16">
                    <!-- Left Content -->
                    <div>
                        <h1 class="text-4xl lg:text-6xl font-black text-white leading-tight mb-8">
                            KUPING DJ PICKS<br>
                            MIXTAPE &<br>
                            ALBUM
                        </h1>
                        
                        <!-- Scroll Indicator -->
                        <div class="flex items-center gap-2 text-white pt-8">
                            <span class="text-sm uppercase tracking-wider">Scroll Down</span>
                            <img src="/public/images/mouse-white.svg" alt="Scroll" class="w-6 h-6">
                        </div>
                    </div>
                    
                    <!-- Right Content -->
                    <div>
                        <p class="text-white/80 text-sm mb-8 max-w-md ml-auto pb-12">
                            Explore the best mixtapes and albums curated just for you by Kuping DJ! Discover unique sounds and elevate your music experience.
                        </p>
                        
                        <!-- Kutipan Card -->
                        <div class="flex justify-end">
                            <KutipanCard
                                personImage="/images/yudyy.jpg"
                                personName="YUDY YANSYAH (DJ YUDY)"
                                personTitle="KUPING DJ OWNER"
                                quoteText="Gw kumpulin mixtape dan album yang cocok banget untuk dipakai ditrend saat ini"
                            />
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Hero Section with Red Background -->
            <section class="relative bg-[#330100] overflow-hidden h-[440px]">
                
            </section>
            
            <div class="container mx-auto pt-16">
                <h2 class="text-3xl font-bold text-white mb-12 px-10">
                    KUPING DJ<br>
                    PICKS MIXTAPE
                </h2>
                
                <!-- Music Cards Grid -->
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 px-2">
                    <MusicCardBlackmusic 
                        album-cover="/images/cartel.jpeg"
                        artist-avatar="/images/whisnu.jpeg"
                        artist-name="Wisnu Santika"
                        title="Cartel Mixtape Exclusive On Kuping DJ"
                        date="02 July, 2025"
                        bpm="150BPM"
                        price="Rp. 200,000"
                        downloads="123"
                        likes="100"
                        rating="4.5"
                    />
                    
                    <MusicCardBlackmusic 
                        album-cover="/images/music/quepasa.jpg"
                        artist-avatar="/images/whisnu.jpeg"
                        artist-name="Wisnu Santika"
                        title="Que Pasa Mixtape Exclusive On Kuping DJ"
                        date="02 July, 2025"
                        bpm="150BPM"
                        price="Rp. 200,000"
                        downloads="123"
                        likes="100"
                        rating="4.5"
                    />
                    
                    <MusicCardBlackmusic 
                        album-cover="/images/music/Hush.jpg"
                        artist-avatar="/images/weird.jpeg"
                        artist-name="Weird Genius"
                        title="HUSH Mixtape Exclusive On Kuping DJ"
                        date="02 July, 2025"
                        bpm="150BPM"
                        price="Rp. 200,000"
                        downloads="123"
                        likes="100"
                        rating="4.5"
                    />
                    
                    <MusicCardBlackmusic 
                        album-cover="/images/music/lathi.jpg"
                        artist-avatar="/images/weird.jpeg"
                        artist-name="Weird Genius"
                        title="Lathi Mixtape Exclusive On Kuping DJ"
                        date="02 July, 2025"
                        bpm="150BPM"
                        price="Rp. 200,000"
                        downloads="123"
                        likes="100"
                        rating="4.5"
                    />
                </div>
            </div>

            <div class="container mx-auto py-12 px-10">
                <h2 class="text-3xl font-bold text-white mb-12">
                    KUPING DJ<br>
                    PICKS ALBUM
                </h2>
                    <!-- Horizontal Scroll Album Wrapper -->
                <div class="flex gap-4 overflow-x-auto pb-4">
                <!-- Album Cards Container -->
                <div class="flex gap-4 min-w-max">
                    <!-- Album 1 -->
                     <div class="flex gap-4 bg-white p-4 w-[670px]">
                    <!-- Album Cover -->
                    <div class="flex-shrink-0">
                        <MusicCardMusic 
                        album-cover="/images/youandme.png" 
                        title="You And Me Album Exclusive On Kuping DJ" 
                        date="02 July, 2025" 
                        price="Rp. 200,000 (bundling Price)" 
                        />
                    </div>

                    <!-- Tracks Grid -->
                    <div class="flex-1 max-h-[476px] overflow-y-auto">
                        <div class="grid grid-cols-2 gap-2">
                        <MusicCardPromotion 
                            date="03, Jul 2025" 
                            capacity="80 Mb" 
                        />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 1" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 2" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 3" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 4" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 5" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 6" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 7" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        </div>
                    </div>
                    </div>
                    

                    <!-- Album 2 -->
                    <div class="flex gap-4 bg-white p-4 w-[670px]">
                    <!-- Album Cover -->
                    <div class="flex-shrink-0">
                        <MusicCardMusic 
                        album-cover="/images/go.png" 
                        title="$GO Album Exclusive On Kuping DJ" 
                        date="02 July, 2025" 
                        price="Rp. 200,000 (bundling Price)" 
                        />
                    </div>

                    <!-- Tracks Grid -->
                    <div class="flex-1 max-h-[476px] overflow-y-auto">
                        <div class="grid grid-cols-2 gap-2">
                        <MusicCardPromotion 
                            date="03, Jul 2025" 
                            capacity="80 Mb" 
                        />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 1" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 2" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 3" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 4" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 5" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 6" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        <MusicCardPlay duration="3 Min, 20 Sec" title="Music 7" date="03, Jul 2025" capacity="5 Mb" price="10.000" />
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script setup>

</script>

<style scoped>
</style>