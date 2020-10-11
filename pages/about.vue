<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        about
      </h1>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
  head() {
    return {
      title: 'About',
      meta: [
        {
          hid: 'description',
          name: 'description',
          contnet: 'This is the description.'
        }
      ]
    }
  }
}
</script>

<style scoped>
h1 {
  color: aliceblue;
}
</style>