<template>
  <meeting-tiles></meeting-tiles>
  <creator-tiles></creator-tiles>
</template>

<script>
import MeetingTiles from "./components/MeetingTiles.vue";
import CreatorTiles from "./components/CreatorTiles.vue";

export default {
  name: "App",
  components: {
    MeetingTiles,
    CreatorTiles,
  },
};
</script>

<style>
#app {
  font-family: sofia-pro, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #fafafa;
  width: 100%;
  height: 100%;
  padding: 50px;
}
</style>
