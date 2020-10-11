<template>
  <div>

    <div class="hero">
      <datocms-image v-if="data" class="hero__image" :data="data.homepage.coverImage.responsiveImage" />
      <div class="wrapper hero__text">
        <h1 v-if="data">{{ data.homepage.title }}</h1>
        <a href="#gallery" class="btn">View Gallery</a>
      </div>
    </div>

    <div v-if="data" class="wrapper">

      <Intro v-bind:body="data.homepage.intro" id="about"/>
      
      <Gallery v-bind:gallery="data.homepage.gallery" id="gallery"/>

      <Meet
        v-if="data"
        v-bind:title="data.homepage.aboutTitle" 
        v-bind:body="data.homepage.aboutBody" 
        v-bind:image="data.homepage.profileImage.responsiveImage"
      />
     
    </div>

    

  </div>
</template>

<script>
import { request } from "../datocms"
import { Image } from "vue-datocms"
import Gallery from "../components/Gallery"
import Intro from "../components/Intro"
import Meet from "../components/Meet"

const HOMEPAGE_QUERY = `query MyQuery {
  homepage {
    title
    intro(markdown: true)
    aboutTitle
    aboutBody(markdown: true)
    profileImage {
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
    coverImage {
      responsiveImage {
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
    gallery {
      responsiveImage(imgixParams: {maxW: 1200}) {
        alt
        aspectRatio
        base64
        bgColor
        height
        sizes
        src
        srcSet
        title
        webpSrcSet
        width
      }
    }
  }
}`

export default {
  name: "Home",
  components: {
    "datocms-image": Image,
    Gallery,
    Intro,
    Meet
  },
  
  async mounted() {
    try {
      this.data = await request({
        query: HOMEPAGE_QUERY
      });
    } catch (e) {
      this.error = e;
      console.log(e)
    }
    this.loading = false;
  },
  data: () => ({
    data: null,
    error: null,
    loading: true,
  }),
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

.hero {
  height: 56rem;
  position: relative;
  display: flex;
  align-items: flex-end;
  background-color: #252427;
}

.hero__image {
  position: absolute !important;
  z-index: 0;
  height: 100%;
}

.hero__image img {
  object-fit: cover;
  height: 100%;
  width: 100%;
  object-position: center;
  opacity: .6;
  pointer-events: none;
}

.hero__text {
  position: relative;
  z-index: 2;
  margin-bottom: 4rem;
}

.btn {
  color: #ffffff;
  border: 1.5px solid #ffffff;
  padding: 1rem 2.4rem;
  text-transform: uppercase;
  display: inline-block;
  letter-spacing: 2px;
  transition: all .2s;
}

.btn:hover {
  background-color: #ffffff;
  color: #49484c;
}

h1 {
  font-size: 3.6rem;
  color: white;
  text-transform: uppercase;
  letter-spacing: 4px;
  margin-bottom: 1.8rem;
}
@media screen and (max-width: 600px) {
  .hero {
    height: 48rem;
  }
}
</style>
