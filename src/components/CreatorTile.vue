<template>
  <div
    class="
      basis-[47%]
      sm:basis-[30%]
      bg-white
      rounded-tl-2xl rounded-br-2xl
      w-[15%]
      max-w-[261px]
      h-auto
      hover:cursor-pointer
    "
  >
    <img
      :src="require(`../assets/imgs/${creator.profileImg}`)"
      :alt="creator.name"
      class="
        w-full
        h-auto
        rounded-tl-2xl rounded-br-2xl
        z-10
        object-cover object-center
      "
    />

    <!-- Main Text -->
    <div class="text-sm sm:p-4 pt-1 leading-4">
      <p
        class="text-lg sm:text-[15px] font-semibold mb-2 sm:mb-0 leading-tight"
      >
        {{ creator.name }}
      </p>
      <p class="mb-2">{{ creator.location }}</p>
      <p class="mb-5 sm:mb-2">{{ creator.job }}</p>
      <p class="font-semibold mb-3 hidden sm:block">
        {{ creator.company }}
      </p>
      <div>
        <i class="fa-solid fa-star inline text-meeow-secondary mr-2"></i>
        <p class="font-semibold inline mr-1">{{ creator.rank }}</p>
        <p class="inline">{{ creator.rankNum }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CreatorTile",
  props: ["creator"],
};
</script>