<template>
  <section class="intro">
    <p class="accent-text">About The Gallery</p>
    <div v-html="body" />
  </section>
</template>

<script>
export default {
  name: "Intro",
  props: ["body"]
}
</script>

<style scoped>
.intro {
  padding: 14rem 0;
  text-align: center;
  font-size: 2rem;
  max-width: 60ch;
  margin: 0 auto;
}

@media screen and (max-width: 979px) {
  .intro {
    padding: 10rem 0;
  }
}

@media screen and (max-width: 600px) {
  .intro {
    padding: 8rem 0;
  }
}
</style>