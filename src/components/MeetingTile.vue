<template>
  <div
    class="
      basis-full
      sm:basis-[47%]
      lg:basis-[30%]
      bg-white
      max-w-[409px]
      h-[413px]
      max-h-[413px]
      rounded-tl-2xl rounded-br-2xl
      text-left
      z-0
      hover:cursor-pointer
      mb-12
      sm:mb-5
      flex flex-col
      content-end
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
        lg:text-[#9F9F9F]
        hover:text-meeow-primary
        group
      "
    >
      <i class="fa-solid fa-heart text-lg"></i>
      <span
        class="
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
          lg:group-hover:visible
        "
        >Add to favorites</span
      >
    </div>

    <!-- Meeting Flair & Placeholder -->
    <div
      class="
        bg-black
        rounded-full
        border
        text-white
        w-max
        min-h-7
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
    <div class="h-7 sm:-mt-4 sm:-mb-8" v-else></div>

    <!-- Main Text -->
    <h6
      class="
        font-semibold
        text-[22px]
        sm:text-lg
        tracking-tight
        leading-7
        sm:leading-6
        mt-5
        padding
        mb-2
      "
    >
      {{ meeting.title }}
    </h6>

    <!-- Date, Time, Spaces -->
    <div class="text-base sm:text-sm padding">
      <p class="xl:inline">{{ meeting.date }}</p>
      <p class="font-semibold xl:inline xl:ml-2">{{ meeting.spaces }}</p>
    </div>

    <!-- Meeting Host Info -->
    <div class="flex flex-wrap mt-6 sm:mt-auto padding">
      <img
        :src="require(`../assets/imgs/${meeting.hostImg}`)"
        alt="meeting.meetingHost"
        class="
          h-[58px]
          w-[58px]
          sm:h-[40px] sm:w-[40px]
          rounded-br-lg rounded-tl-lg
          mr-2
        "
      />

      <div class="text-base sm:text-sm pb-5">
        <p>{{ meeting.meetingHost }}</p>
        <p>
          <i class="fa-solid fa-star text-meeow-secondary"></i>
          {{ meeting.hostType }}
        </p>
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
/* can't seem to get px-0 on mobile and sm:px-5 to work */
@media only screen and (min-width: 640px) {
  .padding {
    padding: 0 20px;
  }
}
</style>