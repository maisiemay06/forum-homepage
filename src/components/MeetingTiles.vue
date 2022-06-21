<template>
  <h1 class="text-6xl tracking-tight font-semibold text-left mb-10">
    Time for you to find interesting Meeows, <br />
    created by interesting new people
  </h1>
  <h4 class="text-2xl text-left mb-10">
    Meet in groups of no more than 4, to have real conversations
  </h4>

  <div class="text-left border-b border-black pb-5 mb-14">
    <a
      class="
        text-sm
        px-5
        py-3
        my-2
        mr-5
        rounded-full
        bg-transparent
        hover:bg-white
      "
      >All</a
    >
    <a
      class="
        text-sm
        px-5
        py-3
        my-2
        mr-5
        rounded-full
        bg-transparent
        hover:bg-white
      "
      >Subject</a
    >
    <a
      class="
        text-sm
        px-5
        py-3
        my-2
        mr-5
        rounded-full
        bg-transparent
        hover:bg-white
      "
      >Today</a
    >
    <a
      class="
        text-sm
        px-5
        py-3
        my-2
        mr-5
        rounded-full
        bg-transparent
        hover:bg-white
      "
      >Next week</a
    >
  </div>

  <div class="flex flex-wrap gap-x-8 gap-y-12">
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
