<template>
  <footer>
    <nav class="wrapper">
      <ul>
        <li><a href="#about">About</a></li>
        <li><a href="#gallery">Gallery</a></li>
        <li><a href="#meet">Meet Me</a></li>
      </ul>
    </nav>
  </footer>
</template>

<script>
export default {
  name: "SiteFooter"
}
</script>

<style scoped>
footer {
  background-color: #252427;
  padding: 1rem 0;
}

ul {
  display: flex;
  justify-content: center;
  text-align: center;
}

li {
  margin: 0 2rem;
  list-style: none;
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