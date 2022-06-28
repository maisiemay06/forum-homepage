<template>
  <!-- Main Nav -->
  <nav class="z-100 navbar">
    <div
      class="
        w-full
        flex
        justify-between
        items-center
        px-6
        pt-14
        pb-3
        lg:px-20 lg:pt-5 lg:pb-5
        border-b
        bg-white
        h-[100px]
        lg:h-[90px]
      "
    >
      <img
        src="../assets/imgs/meeow-logo.png"
        alt="Meeow logo"
        class="h-[18px] w-auto mr-auto lg:mr-4"
      />
      <a
        href=""
        class="
          hidden
          lg:inline-block
          text-[15px]
          bg-transparent
          rounded-full
          px-8
          py-3
          hover:bg-[#F4F4F4]
          transition
          duration-300
          ease-in
        "
        >How Meeow works</a
      >
      <a
        href=""
        class="
          hidden
          lg:inline-block
          text-[15px]
          bg-transparent
          rounded-full
          px-7
          py-3
          hover:bg-[#F4F4F4]
          transition
          duration-300
          ease-in
          mr-auto
        "
        >Browse Subjects</a
      >
      <div class="hidden lg:inline-block mr-12 group">
        <i
          class="fa-solid fa-star text-xl"
          @click="() => openModal('points')"
        ></i>
        <span
          class="
            bg-black
            text-white
            rounded-full
            invisible
            px-2
            py-1
            text-xs
            absolute
            top-[68%]
            -ml-9
            group-hover:visible
          "
          >Points</span
        >
      </div>
      <div class="hidden lg:inline-block mr-12 group">
        <i class="fa-solid fa-calendar text-xl"></i>
        <span
          class="
            bg-black
            text-white
            rounded-full
            invisible
            px-2
            py-1
            text-xs
            absolute
            top-[68%]
            -ml-10
            group-hover:visible
          "
          >Calendar</span
        >
      </div>
      <button
        class="
          hidden
          lg:inline-block
          border-2 border-black
          hover:border-3 hover:border-black
          rounded-full
          px-7
          py-3
          mr-5
          transition
          duration-300
          ease-in
        "
      >
        Login
      </button>
      <button
        class="
          bg-meeow-primary
          hover:bg-meeow-dark
          text-white
          rounded-full
          px-5
          py-1
          lg:px-7 lg:py-3
          text-[15px]
          transition
          duration-300
          ease-in
        "
      >
        Join Meeow
      </button>
      <i
        class="fa-solid fa-ellipsis-vertical text-3xl ml-4 lg:hidden"
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
        top-[100px]
        lg:top-[90px]
        h-[55px]
        lg:px-20 lg:py-3 lg:h-[80px] lg:drop-shadow-md
      "
    >
      <input
        type="text"
        placeholder="Search for subjects and people"
        class="
          w-max
          placeholder:text-black
          px-6
          py-2
          flex-1
          lg:rounded-full lg:border-2 lg:border-black
        "
      />
      <i
        class="
          fa-solid fa-circle-xmark
          text-[#D8D8D8]
          mr-2
          lg:relative lg:-left-16
        "
      ></i>
      <button
        class="
          bg-black
          text-white
          h-[55px]
          w-[55px]
          lg:relative lg:-left-16 lg:rounded-full lg:h-9 lg:w-9
        "
      >
        <i class="fa-solid fa-magnifying-glass"></i>
      </button>
      <button
        class="
          hidden
          lg:inline-block
          bg-black
          text-white text-sm
          rounded-full
          -ml-10
          px-7
          py-3
        "
      >
        Create a Meeow
      </button>
    </div>

    <!-- Countdown Bar -->
    <!-- Can't get the padding on the right hand side of the page so had to set width to 90% but doesn't work for all screen sizes.  -->
    <div class="w-full lg:px-20 border-box">
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
          top-[155px]
          lg:h-[80px] lg:top-[170px] lg:justify-center lg:w-[90%]
          border-box
        "
      >
        <p class="hidden lg:inline-block font-semibold text-[15px] mr-5">
          on-demand networking in
        </p>
        <p class="text-3xl sm:text-[50px] font-semibold lg:mr-5">13:52</p>
        <button
          class="
            text-[15px]
            lg:bg-white lg:text-meeow-primary lg:mr-5 lg:px-4 lg:py-1
            rounded-full
          "
        >
          Open on-demand networking
        </button>
        <img
          src="../assets/imgs/info-bubble.png"
          alt=""
          @click="() => openModal('ondemand')"
          class="hover:cursor-pointer"
        />
        <a
          class="hidden lg:inline-block text-xs ml-2 hover:cursor-pointer"
          @click="() => openModal('ondemand')"
          >Tell me more about this?</a
        >
      </div>
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
  },
};
</script>

<style scoped>
</style>