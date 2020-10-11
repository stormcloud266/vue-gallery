<template>
  <header class="wrapper">
    <nav>
      <ul>
        <li><a href="#about">About</a></li>
        <li><a href="#gallery">Gallery</a></li>
        <li><a href="#meet">Meet Me</a></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "SiteHeader"
}
</script>

<style scoped>
header {
  position: absolute;
  left: 0; right: 0; top: 0;
  color: white;
  padding-top: 2rem;
  padding-bottom: 2rem;
  z-index: 999;
}

ul {
  display: flex;
  justify-content: center;
  width: 100%;
}

li {
  list-style: none;
  margin: 0 2rem;
}

a {
  color: white;
  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: 1.5rem;
}

@media screen and (max-width: 600px) {
  li {
    margin: 0 1rem 0 0;
  }
  li:last-child {
    margin:0;
  }
}
</style>