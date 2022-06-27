<template>
  <div class="pl-6 py-12 pr-5 sm:p-12 mt-[210px] text-center">
    <h1 class="sm:text-6xl text-4xl tracking-tight font-semibold mb-10">
      Meeow. The real conversation platform.
    </h1>
    <h4 class="sm:text-2xl text-lg mb-5">
      Find out how our revolutionary AI matching helps you find and meet people
      who're talking about the subjects you love.
    </h4>
    <img
      src="../assets/imgs/tolstoy-holder.png"
      alt="tolstoy video placeholder"
      class="mb-5 h-[540px] object-cover object-center rounded-lg mx-auto"
    />
    <button
      class="
        bg-meeow-primary
        rounded-full
        px-8
        py-3
        text-sm text-white
        mr-2
        sm:mr-5
      "
    >
      Join Meeow
    </button>
    <button
      class="
        hidden
        sm:inline-block
        border border-black
        rounded-full
        px-8
        text-sm
        py-3
      "
    >
      Create your own Meeow
    </button>
    <button
      class="sm:hidden border border-black rounded-full px-8 text-sm py-3"
    >
      Create a Meeow
    </button>
  </div>
</template>

<script>
export default {
  name: "MainTitle",
  props: ["title", "subtitle"],
};
</script>