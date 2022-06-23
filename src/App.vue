<template>
  <advert-full></advert-full>
  <div class="p-6 sm:p-12">
    <meeting-tiles></meeting-tiles>
    <creator-tiles></creator-tiles>
  </div>
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
  text-align: center;
  background-color: #fff;
  width: 100%;
  height: 100%;

  max-width: 100vw;
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
