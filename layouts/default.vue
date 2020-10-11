<template>
  <div>
    <SiteHeader />
    <Nuxt />
    <SiteFooter />
  </div>
</template>

<script>
import SiteHeader from '@/components/SiteHeader'
import SiteFooter from '@/components/SiteFooter'

export default {
  components: {
    SiteHeader,
    SiteFooter
  }
}
</script>

<style>
html {
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
  font-size: 1.7rem;
  line-height: 1.7;
  color: #49484c;
  font-family: 'Raleway', sans-serif;
}
a {
  text-decoration: none;
}
.wrapper {
  width: 100%;
  max-width: 120rem;
  margin-left: auto;
  margin-right: auto;
  padding-left: 1.4rem;
  padding-right: 1.4rem;
}

.accent-text {
  font-size: 1.5rem;
  text-transform: uppercase;
  color: #717070;
  margin-bottom: 1rem;
  display: inline-block;
}

.accent-text::before,
.accent-text::after {
  content: "";
  display: block;
  width: 4rem;
  height: 1px;
  background-color: #ababab;
  position: relative;
}
.accent-text::before {
  top: 1.2rem;
  left: -1rem; 
  transform: translateX(-100%);
}

.accent-text::after {
  top: -1.2rem;
  right: -100%; 
  transform: translateX(1rem);

}
</style>
