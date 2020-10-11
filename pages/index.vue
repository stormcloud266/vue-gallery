<template>
  <div>
    <div class="wrapper">
      <h1>{{ data.homepage.title }}</h1>
      <div v-html="data.homepage.intro" />
      <datocms-image :data="data.homepage.profile.responsiveImage" />
    </div>
  </div>
</template>

<script>
import { request } from "../datocms"
import { Image } from "vue-datocms"

const HOMEPAGE_QUERY = `query MyQuery {
  homepage {
    title
    intro(markdown: true)
    profile {
      responsiveImage(imgixParams: {maxW: 700}) {
        srcSet
        webpSrcSet
        sizes
        src
        width
        aspectRatio
        alt
        title
        base64
      }
    }
  }
}`

export default {
  components: {
    "datocms-image": Image
  },
  data: () => ({
    data: null,
    error: null,
    loading: true,
  }),
  async mounted() {
    try {
      this.data = await request({
        query: HOMEPAGE_QUERY
      });
    } catch (e) {
      console.error(e)
      this.error = e;
    }
    this.loading = false;
  }
}
</script>

<style>
img {
  max-width: 700px;
}
</style>
