<template>
  <img
    :src="require(`../assets/imgs/${adImg}`)"
    alt=""
    class="
      w-full
      h-[223px]
      object-cover object-right
      mb-1
      sm:rounded-tl-2xl sm:rounded-br-2xl sm:h-auto sm:w-[49%]
    "
  />
</template>

<script>
export default {
  name: "AdvertSmall",
  props: ["adImg"],
};
</script>