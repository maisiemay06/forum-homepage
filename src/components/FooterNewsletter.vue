<template>
  <div
    class="
      footer-container
      bg-meeow-primary
      text-white
      p-6
      sm:p-12
      mt-5
      w-full
      lg:flex
      justify-between
    "
  >
    <h1
      class="
        sm:text-6xl
        text-3xl
        tracking-tight
        font-semibold
        text-left
        lg:w-2/5
        mb-3
        sm:mb-5
        lg:mb-0
      "
    >
      Stay up-to-date with all things Meeow
    </h1>
    <div class="text-left email-input">
      <label for="newsletter-email" class="block text-lg mb-3 lg:mb-0"
        >Sign up to receive updates about Meeow</label
      >
      <input
        type="email"
        name="newsletter-email"
        id="newsletter-email"
        placeholder="Email address"
        class="rounded-full h-[50px] mt-3 mr-3 px-5 text-black text-sm w-full"
      />
      <input
        type="button"
        value="Submit"
        class="
          text-meeow-primary
          bg-white
          hover:bg-zinc-100 hover:cursor-pointer
          transition
          duration-75
          ease-in
          rounded-full
          h-[50px]
          px-8
          text-sm
          mt-3
          lg:mt-0
        "
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "FooterNewsletter",
};
</script>

<style scoped>
/* Can't get these styles to work with tailwind */
.footer-container {
  padding-top: 5rem;
  padding-bottom: 5rem;
}

#newsletter-email::placeholder {
  color: black;
}

@media only screen and (min-width: 768px) {
  .footer-container {
    padding-top: 5rem;
    padding-bottom: 8rem;
    align-items: center;
  }
  .email-input,
  #newsletter-email {
    width: 60%;
  }
}
</style>