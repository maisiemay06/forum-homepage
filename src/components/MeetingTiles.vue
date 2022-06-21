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
        transition
        ease-in
        duration-100
      "
      >All</a
    >
    <a class="text-sm px-5 py-3 my-2 mr-5 rounded-full bg-transparent group"
      >Subject <i class="fa-solid fa-chevron-down"></i>
      <ul
        class="
          bg-white
          hidden
          group-hover:block
          absolute
          z-20
          left-[125px]
          transition
          ease-in
          duration-1000
          shadow-md
          rounded-tl-2xl rounded-br-2xl
        "
      >
        <li
          class="
            w-[180px]
            px-4
            py-2
            my-1
            hover:bg-[#F7F7F7]
            transition
            ease-in
            duration-100
          "
        >
          Category 1
        </li>
        <li
          class="
            w-[180px]
            px-4
            py-2
            my-1
            hover:bg-[#F7F7F7]
            transition
            ease-in
            duration-100
          "
        >
          Category 2
        </li>
        <li
          class="
            w-[180px]
            px-4
            py-2
            my-1
            hover:bg-[#F7F7F7]
            transition
            ease-in
            duration-100
          "
        >
          Category 3
        </li>
        <li
          class="
            w-[180px]
            px-4
            py-2
            my-1
            hover:bg-[#F7F7F7]
            transition
            ease-in
            duration-100
          "
        >
          Category 4
        </li>
        <li
          class="
            w-[180px]
            px-4
            py-2
            my-1
            hover:bg-[#F7F7F7]
            transition
            ease-in
            duration-100
          "
        >
          Category 5
        </li>
        <li
          class="
            w-[180px]
            px-4
            py-2
            my-1
            hover:bg-[#F7F7F7]
            transition
            ease-in
            duration-100
          "
        >
          Category 6
        </li>
        <li
          class="
            w-[180px]
            px-4
            py-2
            my-1
            hover:bg-[#F7F7F7]
            transition
            ease-in
            duration-100
          "
        >
          Category 7
        </li>
      </ul></a
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
        transition
        ease-in
        duration-100
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
        transition
        ease-in
        duration-100
      "
      >This week</a
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
        transition
        ease-in
        duration-100
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
