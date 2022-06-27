<template>
  <div
    class="
      w-full
      h-[100vh]
      bg-black/80
      absolute
      top-0
      flex
      justify-center
      items-center
    "
    @click="closeModal"
  >
    <div
      class="
        bg-white
        rounded-tl-2xl rounded-br-2xl
        text-left text-sm
        w-4/5
        p-6
        lg:w-[296px]
      "
    >
      <p>{{ modalContent }}</p>
      <button
        class="
          bg-meeow-primary
          text-white
          px-7
          py-2
          text-[15px]
          rounded-full
          mt-4
        "
        @click="closeModal"
      >
        {{ modalBtnContent }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalTemplate",
  props: ["closeModal", "modalContent", "modalBtnContent"],
};
</script>