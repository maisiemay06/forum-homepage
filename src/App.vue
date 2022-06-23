<template>
  <!-- Large Ad -->
  <advert-full></advert-full>

  <!-- Meeting & Creator Tiles -->
  <div class="p-6 sm:p-12">
    <meeting-tiles></meeting-tiles>
    <creator-tiles></creator-tiles>
  </div>

  <!-- Section Title -->
  <div class="p-6 sm:p-12 hidden sm:block">
    <h1
      class="sm:text-6xl text-4xl tracking-tight font-semibold text-left mb-10"
    >
      New business, collaboration, support, ideas, opinion, insight, learning,
      promotion, understanding, opportunies...
    </h1>
    <h4 class="sm:text-2xl text-lg text-left mb-10">
      Find them all, on Meeow.
    </h4>
    <button
      class="bg-meeow-primary rounded-full px-8 py-3 text-sm text-white mr-5"
    >
      Join Meeow
    </button>
    <button class="border border-black rounded-full px-8 text-sm py-3">
      Create your own Meeow
    </button>
  </div>

  <!-- Small Ads -->
  <div class="flex sm:p-12 gap-8 advert-small">
    <advert-small adImg="ad-img-2.png"></advert-small>
    <advert-small adImg="ad-img-3.png"></advert-small>
  </div>
</template>

<script>
import MeetingTiles from "./components/MeetingTiles.vue";
import CreatorTiles from "./components/CreatorTiles.vue";
import AdvertFull from "./components/AdvertFull.vue";
import AdvertSmall from "./components/AdvertSmall.vue";

export default {
  name: "App",
  components: {
    MeetingTiles,
    CreatorTiles,
    AdvertFull,
    AdvertSmall,
  },
};
</script>

<style>
#app {
  font-family: sofia-pro, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #fff;
  width: 100%;
  height: 100%;
  max-width: 100vw;
}

.advert-small {
  flex-direction: column;
}

@media screen and (min-width: 640px) {
  #app {
    background-color: #fafafa;
  }
  .advert-small {
    flex-direction: row;
  }
}
</style>
