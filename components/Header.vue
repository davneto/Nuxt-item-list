<template>
  <header>
    <nav>
      <ul>
        <li><nuxt-link to="/">Items</nuxt-link></li>
        <li><nuxt-link to="/about">About</nuxt-link></li>
      </ul>
    </nav>

  </header>
</template>

<script>
</script>

<style scoped>

  header {
    width: 100%;
    padding: 15px;
    background-color:#ccc;
    border-bottom: #aaa;
  }

  ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  li {
     padding: 0 15px;
  }

</style>

