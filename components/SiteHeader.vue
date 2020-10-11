<template>
  <header class="wrapper">
    <nuxt-link to="/" class="logo">Logo</nuxt-link>
    <nav>
      <ul>
        <li><nuxt-link to="/">Home</nuxt-link></li>
        <li><nuxt-link to="/about">About</nuxt-link></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {

}
</script>

<style scoped>
header {
  background-color: #ffffff;
  padding-top: 2rem;
  padding-bottom: 2rem;
  display: flex;
  justify-content: space-between;
}

ul {
  display: flex;
}

li {
  list-style: none;
  margin-left: 4rem;
}

.logo {
  font-weight: 700;
  text-transform: uppercase;
}
</style>