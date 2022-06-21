<template>
  <div
    class="
      bg-white
      w-[409px]
      h-[413px]
      rounded-tl-2xl rounded-br-2xl
      text-left
      z-0
      hover:cursor-pointer
    "
  >
    <img
      :src="require(`../assets/imgs/${tile.meetingImg}`)"
      :alt="tile.title"
      class="w-full h-[229px] rounded-tl-2xl rounded-br-2xl z-10"
    />

    <div
      class="
        fav-btn
        bg-white
        rounded-full
        w-[45px]
        h-[45px]
        shadow
        text-center
        py-2
        -mt-8
        -mb-5
        ml-[21.5rem]
        z-20
        relative
        text-[#9F9F9F]
        hover:text-meeow-primary
      "
    >
      <i class="fa-solid fa-heart text-lg"></i>
      <span
        class="
          fav-btn-text
          invisible
          w-[118px]
          h-[23px]
          p-1
          bg-black
          text-white text-center
          rounded-full
          absolute
          z-20
          top-[105%]
          left-[50%]
          -ml-[59px]
          text-xs
        "
        >Add to favorites</span
      >
    </div>
    <div
      class="
        bg-meeow-primary
        rounded-full
        border
        text-white
        w-max
        py-1
        px-3
        text-xs
        -mt-8
        ml-5
        -mb-3
        z-20
        relative
      "
      v-if="tile.flair"
    >
      {{ tile.flair }}
    </div>

    <div class="p-5 flex flex-col align-between mt-3">
      <h6 class="font-semibold text-lg mb-[8px] tracking-tight">
        {{ tile.title }}
      </h6>
      <div class="text-[14px] mb-5">
        <p class="inline">{{ tile.date }}</p>
        <p class="font-semibold inline ml-2">{{ tile.spaces }}</p>
      </div>
      <div class="flex flex-wrap mt-auto mb-[26px]">
        <img
          :src="require(`../assets/imgs/${tile.hostImg}`)"
          :alt="host"
          class="h-[40px] w-[40px] rounded-br-xl rounded-tl-xl mr-2"
        />
        <div class="text-xs">
          <p>{{ tile.host }}</p>
          <p>
            <i class="fa-solid fa-star text-meeow-secondary"></i>
            {{ tile.hostType }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MeetingTile",
  props: ["tile"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.fav-btn:hover .fav-btn-text {
  visibility: visible;
}
</style>