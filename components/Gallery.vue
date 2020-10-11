<template>
  <div class="gallery" id="gallery">
    <datocms-image v-for="image in gallery" v-bind:key="image.responsiveImage.src" :data="image.responsiveImage" />
  </div>
</template>

<script>
import { Image } from "vue-datocms"

export default {
  name: "Gallery",
  components: {
    "datocms-image": Image,
  },
  props: ["gallery"]
}
</script>

<style>
.gallery {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: 300px;
  gap: 1rem;
}
.gallery img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.gallery > div:nth-child(1) {
  grid-column: span 1;
}

.gallery > div:nth-child(2) {
  grid-column: span 1;
  grid-row: span 2;
}

.gallery > div:nth-child(3) {
  grid-column: span 2;
}


@media screen and (max-width: 979px) {
  .gallery {
    grid-template-columns: repeat(2, 1fr);
  }
  .gallery > div:nth-child(4) {
    grid-row: 2 / 3;
  }
}
@media screen and (max-width: 600px) {
  .gallery {
    grid-auto-rows: 200px;
  }
}
</style>