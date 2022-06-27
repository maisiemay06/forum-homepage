<template>
  <div class="pl-6 py-12 pr-5 sm:p-12 text-left">
    <h1
      class="sm:text-6xl text-4xl tracking-tight font-semibold text-left mb-10"
    >
      {{ title }}
    </h1>
    <h4 class="sm:text-2xl text-lg text-left mb-10">
      {{ subtitle }}
    </h4>
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
  name: "TitleDivider",
  props: ["title", "subtitle"],
};
</script>