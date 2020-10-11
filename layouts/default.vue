<template>
  <div>
    <SiteHeader />
    <Nuxt />
  </div>
</template>

<script>
import SiteHeader from '@/components/SiteHeader'

export default {
  components: {
    SiteHeader
  },
  head() {
    return {
      title: 'Home',
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

<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 62.5%;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-size: 1.6rem;
  line-height: 1.5;
}
a {
  text-decoration: none;
}
.wrapper {
  width: 100%;
  max-width: 120rem;
  margin-left: auto;
  margin-right: auto;
}
</style>
