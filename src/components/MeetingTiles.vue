<template>
  <div class="flex flex-wrap gap-x-9 gap-y-12 p-9">
    <template v-for="tile in tileContent" :key="tile.id">
      <meeting-tile :tile="tile"></meeting-tile>
    </template>
  </div>
</template>

<script>
import MeetingTile from "./MeetingTile.vue";
import TileContent from "./TileContent";

export default {
  name: "MeetingTiles",
  components: {
    MeetingTile,
  },
  data() {
    return {
      tileContent: TileContent,
    };
  },
};
</script>

<style scoped>
</style>
