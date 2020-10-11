<template>

  <div class="meet" id="meet">

    <div  class="meet__image-container">
      <datocms-image :data="image" class="meet__image"/>
    </div>
  
    
    <div class="meet__text">
      <h2>{{ title }}</h2>
      <div v-html="body" />
    </div>
  </div>
  
</template>

<script>
import { Image } from "vue-datocms"

export default {
  name: "Meet",
  props: ["title", "body", "image"],
  components: {
    "datocms-image": Image,
  },
}
</script>

<style>

.meet {
  display: flex;
  padding: 14rem 0;
  position: relative;
  align-items: center;
}

.meet__image-container {
  flex: 1;
  position: relative;
  margin-left: 1.4rem;
}

.meet__image-container::before {
  content: "";
  display: block;
  width: 100%;
  height: 99%;
  border: 1px solid #b3b0b0;
  position: absolute;
  top: -1.4rem;
  left: -1.4rem;
  border-radius: 2px;
}

.meet__image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: left;
  border-radius: 2px;
}

.meet__text {
  flex: 1;
  padding-left: 4rem;
}

.meet__text p {
  margin-top: 1.4rem;
}

@media screen and (max-width: 979px) {
  .meet {
    padding: 10rem 0;
    flex-direction: column;
    max-width: 60ch;
    margin-left: auto;
    margin-right: auto;
  }
  .meet__text {
    padding-left: 0;
    padding-top: 4rem;
  }
}
@media screen and (max-width: 600px) {
  .meet {
    padding: 8rem 0;
  }
}

</style>