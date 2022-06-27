<template>
  <!-- Main Nav -->
  <nav :class="{ 'is-hidden': !showNavbar }">
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
      <i
        class="fa-solid fa-ellipsis-vertical text-3xl ml-4"
        @click="toggleNavMenu"
      ></i>
    </div>

    <!-- Nav Menu -->
    <div
      v-if="showNavMenu"
      class="
        z-20
        absolute
        bg-white
        right-0
        h-[100vh]
        w-2/3
        drop-shadow-xl
        pt-28
        pl-10
        text-left
        flex flex-col
        items-start
        text-lg
      "
    >
      <ul>
        <li class="py-3">Favourites</li>
        <li class="py-3">Calendar</li>
        <li class="py-3">Messaging</li>
        <li class="py-3">Tell a Friend</li>
        <li
          class="py-3"
          @click="
            () => {
              openModal('points');
              toggleNavMenu();
            }
          "
        >
          Points
        </li>
      </ul>
      <button class="mt-auto pb-10 flex items-center" @click="toggleNavMenu">
        Close <i class="fa-solid fa-xmark text-3xl ml-2"></i>
      </button>
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
      <img
        src="../assets/imgs/info-bubble.png"
        alt=""
        @click="() => openModal('ondemand')"
      />
    </div>

    <modal-template
      v-if="showModal"
      class="z-30"
      :closeModal="closeModal"
      :modalContent="modalContent"
      :modalBtnContent="modalBtnContent"
    ></modal-template>
  </nav>
</template>

<script>
import ModalTemplate from "./ModalTemplate.vue";

export default {
  name: "NavBar",
  components: {
    ModalTemplate,
  },
  data() {
    return {
      showNavMenu: false,
      showModal: false,
      modalContent: "",
      modalBtnContent: "",
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
    toggleNavMenu() {
      console.log("show");
      this.showNavMenu = !this.showNavMenu;
    },
    openModal(props) {
      if (props === "points") {
        this.modalContent = `Meeow awards every member points for every engagement with the community, helping you to build your reputation as a brilliant networker.
        <br />
        <br />
        As you build your points total and rise through the ranks tobe an
        Ambassador`;
        this.modalBtnContent = "Join now";
      } else if (props === "ondemand") {
        this.modalContent = `AI matched, On-demand networking on Meeow allows you to network with up to 3 new people on the hour, every hour for 45 mins.
        <br />
        <br />
        Only 4 people in each meeting, to ensure good quality conversation.
        <br />
        <br />
        No limit to the number of 4 person meetings at one time, so everyone gets to network when they want to.
        `;
        this.modalBtnContent = "Open on-demand networking";
      }
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    },
    onScroll() {
      const currentScrollPos =
        window.pageYOffset || document.documentElement.scrollTop;

      if (currentScrollPos < 0) {
        return;
      }

      if (Math.abs(currentScrollPos - this.lastScrollPos) < 80) {
        return;
      }

      this.showNavbar = currentScrollPos < this.lastScrollPos;

      this.lastScrollPos = currentScrollPos;
    },
  },
};
</script>

<style scoped>
nav {
  transform: translateY(0);
  transition: transform 300ms ease-out;
}
nav.is-hidden {
  transform: translateY(-100%);
}
</style>