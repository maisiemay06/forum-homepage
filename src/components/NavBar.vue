<template>
  <!-- Main Nav -->
  <nav :class="{ hidden: !showNavbar }">
    <div
      class="
        w-full
        flex
        justify-between
        items-center
        px-6
        pt-14
        pb-3
        border-b
        bg-white
        fixed
        h-[100px]
      "
    >
      <img
        src="../assets/imgs/meeow-logo.png"
        alt="Meeow logo"
        class="h-[18px] w-auto mr-auto"
      />
      <button
        class="bg-meeow-primary text-white rounded-full px-5 py-1 text-[15px]"
      >
        Join Meeow free
      </button>
      <i class="fa-solid fa-ellipsis-vertical text-3xl ml-4"></i>
    </div>

    <!-- Search Bar -->
    <div
      class="
        w-full
        flex
        justify-start
        items-center
        bg-white
        fixed
        top-[100px]
        h-[55px]
      "
    >
      <input
        type="text"
        placeholder="Search for subjects and people"
        class="w-max placeholder:text-black px-6 py-2 flex-1"
      />
      <i class="fa-solid fa-circle-xmark text-[#D8D8D8] mr-2"></i>
      <button class="bg-black text-white h-[55px] w-[55px]">
        <i class="fa-solid fa-magnifying-glass"></i>
      </button>
    </div>

    <!-- Countdown Bar -->
    <div
      class="
        w-full
        flex
        justify-around
        items-center
        bg-meeow-primary
        text-white
        rounded-b-lg
        py-2
        px-6
        fixed
        top-[155px]
      "
    >
      <p class="text-3xl font-semibold">13:52</p>
      <button class="text-sm">Open on-demand networking</button>
      <img src="../assets/imgs/info-bubble.png" alt="" />
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data() {
    return {
      showNavbar: true,
      lastScrollPos: 0,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.onScroll);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.onScroll);
  },
  methods: {
    onScroll() {
      const currentScrollPos =
        window.pageYOffset || document.documentElement.scrollTop;

      if (currentScrollPos < 0) {
        return;
      }

      if (Math.abs(currentScrollPos - this.lastScrollPos) < 100) {
        return;
      }

      this.showNavbar = currentScrollPos < this.lastScrollPos;

      this.lastScrollPos = currentScrollPos;
    },
  },
};
</script>

<style scoped>
</style>