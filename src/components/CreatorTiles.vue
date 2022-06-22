<template>
  <div class="text-left mt-20">
    <h4 class="inline font-semibold text-lg mr-3">
      Interesting Meeow Creators
    </h4>
    <a class="inline text-sm hover:cursor-pointer hover:underline"
      >Explore all <i class="fa-solid fa-chevron-right"></i
    ></a>

    <div class="flex flex-wrap justify-between gap-y-12 mt-5">
      <template v-for="creator in creatorContent" :key="creator.id">
        <creator-tile :creator="creator"></creator-tile>
      </template>
    </div>
  </div>
</template>

<script>
import CreatorTile from "./CreatorTile.vue";
import CreatorCreators from "./CreatorContent";

export default {
  name: "CreatorTiles",
  components: {
    CreatorTile,
  },
  data() {
    return {
      creatorContent: CreatorCreators,
    };
  },
};
</script>