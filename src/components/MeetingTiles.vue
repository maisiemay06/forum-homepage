<template>
  <!-- Section Header -->
  <h1 class="sm:text-6xl text-4xl tracking-tight font-semibold text-left mb-10">
    Time for you to find interesting Meeows, created by interesting new people
  </h1>
  <h4 class="sm:text-2xl text-lg text-left mb-10">
    Meet in groups of no more than 4, to have real conversations
  </h4>

  <!-- Filter Options -->
  <div
    class="
      text-left
      border-b border-black
      pb-5
      mb-14
      overflow-x-auto
      whitespace-nowrap
    "
  >
    <a class="filter-options">All</a>
    <a class="filter-options group"
      >Subject <i class="fa-solid fa-chevron-down"></i>

      <!-- Subject Dropdown Options -->
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
        <li class="dropdown-options">Category 1</li>
        <li class="dropdown-options">Category 2</li>
        <li class="dropdown-options">Category 3</li>
        <li class="dropdown-options">Category 4</li>
        <li class="dropdown-options">Category 5</li>
        <li class="dropdown-options">Category 6</li>
        <li class="dropdown-options">Category 7</li>
      </ul></a
    >

    <a class="filter-options">Today</a>
    <a class="filter-options">This week</a>
    <a class="filter-options">Next week</a>
  </div>

  <!-- Meeting Tiles -->

  <div class="flex flex-wrap gap-y-12 justify-between">
    <transition-group name="fade">
      <template v-for="(meeting, index) in meetingContent" :key="meeting.id">
        <meeting-tile
          :meeting="meeting"
          v-if="index < this.meetingLimit"
        ></meeting-tile>
      </template>
    </transition-group>
  </div>

  <!-- Show More Btn -->
  <button
    class="
      bg-meeow-primary
      rounded-3xl
      text-white text-sm
      px-6
      py-3
      mt-10
      hover:bg-meeow-dark
      transition
      ease-in
      duration-100
    "
    @click="() => (this.meetingLimit += 4)"
    v-if="this.meetingLimit < this.meetingContent.length"
  >
    Show me more
  </button>
</template>

<script>
import MeetingTile from "./MeetingTile.vue";
import MeetingContent from "./MeetingContent";

export default {
  name: "MeetingTiles",
  components: {
    MeetingTile,
  },
  data() {
    return {
      meetingContent: MeetingContent,
      meetingLimit: 4,
    };
  },
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease-in-out;
}
.fade-enter-from,
.fade-enter-to {
  opacity: 0;
}

.filter-options {
  font-size: 0.875rem;
  padding: 0.75rem 1.25rem;
  margin: 0.5rem 1.25rem 0.5rem 0;
  border-radius: 9999px;
  background-color: transparent;
  transition: ease-in 100ms;
}

.filter-options:hover {
  background-color: #fff;
}

.dropdown-options {
  width: 180px;
  padding: 1rem 0.5rem;
  margin: 0.25rem 0;
  transition: ease-in 100ms;
}

.dropdown-options:hover {
  background-color: #f7f7f7;
}

@media screen and (max-width: 640px) {
  .filter-options {
    font-size: 1.125rem;
    background-color: #fafafa;
  }
}
</style>
