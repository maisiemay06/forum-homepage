<template>
  <!-- Section Title -->
  <title-divider
    title="Meeow. The real conversation platform."
    subtitle="Revolutionary AI matching to find and meet online with the people who're talking about subjects you love."
  ></title-divider>
  <!-- Large Ad -->
  <advert-full></advert-full>

  <!-- Meeting & Creator Tiles -->
  <div class="p-6 sm:p-12">
    <meeting-tiles></meeting-tiles>
    <creator-tiles></creator-tiles>
  </div>

  <!-- Section Title -->
  <title-divider
    title="New business, collaboration, support, ideas, opinions, insight, learning, promotion, understanding, opportunities..."
    subtitle="Find them all, on Meeow."
  ></title-divider>

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
import TitleDivider from "./components/TitleDivider.vue";

export default {
  name: "App",
  components: {
    MeetingTiles,
    CreatorTiles,
    AdvertFull,
    AdvertSmall,
    TitleDivider,
  },
};
</script>

<style>
#app {
  font-family: sofia-pro, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #fff;
  text-align: center;
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
