<template>
  <div>
    <div class="wrapper">
    <div class="loading" v-if="loading">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-rotate-clockwise-2" width="28" height="28" viewBox="0 0 24 24" stroke-width="1.5" stroke="#1d1a50" fill="none" stroke-linecap="round" stroke-linejoin="round">
        <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
        <path d="M9 4.55a8 8 0 0 1 6 14.9m0 -4.45v5h5" />
        <line x1="5.63" y1="7.16" x2="5.63" y2="7.17" />
        <line x1="4.06" y1="11" x2="4.06" y2="11.01" />
        <line x1="4.63" y1="15.1" x2="4.63" y2="15.11" />
        <line x1="7.16" y1="18.37" x2="7.16" y2="18.38" />
        <line x1="11" y1="19.94" x2="11" y2="19.95" />
      </svg>
    </div>
    <div v-else-if="error">Something bad happened</div>
    <div v-else>
      <h1>{{ data.homepage.title }}</h1>
      <div v-html="data.homepage.intro" />
      <div class="img">
        <datocms-image :data="data.homepage.profile.responsiveImage" />
      </div>
    </div>
     
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
  name: "Home",
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
      this.error = e;
    }
    this.loading = false;
  }
}
</script>

<style>
.img {
  max-width: 700px;
}
.loading svg {
  animation: 1.5s spin linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(-360deg);
  }
}
</style>
