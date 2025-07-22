<template>
  <div>
    <!-- ID untuk link Home -->
    <div id="home">
      <AllpagecomponentHome />
    </div>

    <!-- ID untuk link Artist -->
    <div id="artist">
      <AllpagecomponentArtist />
    </div>

    <!-- ID untuk link Mixtape -->
    <div id="mixtape">
      <AllpagecomponentNewArrival />
    </div>

    <AllpagecomponentPopularMixtape />

    <!-- ID untuk link Album -->
    <div id="album">
      <AllpagecomponentArrivalAlbum />
    </div>

    <AllpagecomponentExploreGenre />
    <AllpagecomponentKupingDj />
    <AllpagecomponentAfterPurchase />
    <AllpagecomponentTheMagic />
    <AllpagecomponentKutipanSwiper />
    <AllpagecomponentJoinDoms />
    <AllpagecomponentFooter />
  </div>
</template>

<script setup>
// Tidak perlu tambahan script di sini
</script>

<style scoped>
html {
  scroll-behavior: smooth;
}
</style>
