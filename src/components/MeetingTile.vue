<template>
  <div
    class="
      basis-full
      sm:basis-[47%]
      lg:basis-[30%]
      bg-white
      max-w-[409px]
      h-[413px]
      rounded-tl-2xl rounded-br-2xl
      text-left
      z-0
      hover:cursor-pointer
      mb-12
      sm:mb-5
    "
  >
    <img
      :src="require(`../assets/imgs/${meeting.meetingImg}`)"
      :alt="meeting.title"
      class="
        w-full
        h-auto
        rounded-tl-2xl rounded-br-2xl
        z-10
        object-cover object-center
      "
    />

    <!-- Favorite Btn -->
    <div
      class="
        bg-white
        rounded-full
        w-[50px]
        h-[50px]
        sm:w-[45px] sm:h-[45px]
        shadow
        text-center
        py-2
        -mt-8
        ml-[85%]
        z-20
        relative
        text-black
        sm:text-[#9F9F9F]
        hover:text-meeow-primary
        group
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
          z-30
          top-[105%]
          left-[50%]
          -ml-[59px]
          text-xs
          group-hover:visible
        "
        >Add to favorites</span
      >
    </div>

    <!-- Meeting Flair -->
    <div
      class="
        bg-meeow-primary
        rounded-full
        border
        text-white
        w-max
        py-1
        px-3
        text-sm
        sm:text-xs sm:-mt-8 sm:-mb-3 sm:ml-5
        z-20
        relative
      "
      v-if="meeting.flair"
    >
      {{ meeting.flair }}
    </div>

    <!-- Main Text -->
    <div class="sm:p-5 flex flex-col mt-2 sm:mt-0">
      <h6 class="font-semibold text-[22px] sm:text-lg mb-[8px] tracking-tight">
        {{ meeting.title }}
      </h6>
      <div class="text-base sm:text-sm mb-5">
        <p class="sm:inline">{{ meeting.date }}</p>
        <p class="font-semibold sm:inline sm:ml-2">{{ meeting.spaces }}</p>
      </div>

      <!-- Meeting Host -->
      <div class="flex flex-wrap mt-auto mb-[26px] justify-self-end">
        <img
          :src="require(`../assets/imgs/${meeting.hostImg}`)"
          :alt="meeting.meetingHost"
          class="
            h-[58px]
            w-[58px]
            sm:h-[40px] sm:w-[40px]
            rounded-br-lg rounded-tl-lg
            mr-2
          "
        />
        <div class="text-base sm:text-xs">
          <p>{{ meeting.meetingHost }}</p>
          <p>
            <i class="fa-solid fa-star text-meeow-secondary"></i>
            {{ meeting.hostType }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MeetingTile",
  props: ["meeting"],
};
</script>

<style scoped>
</style>