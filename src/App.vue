<template>
  <MeetingTiles />
</template>

<script>
import MeetingTiles from "./components/MeetingTiles.vue";

export default {
  name: "App",
  components: {
    MeetingTiles,
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
}
</style>
