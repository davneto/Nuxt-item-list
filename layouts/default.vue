<template>
  <div>
    <Header />
    <nuxt/>
  </div>
</template>

<script>

import Header from '@/components/Header'

export default{

  components: {
    Header
  }
}


</script>

<style>

body{
  margin:0;
}

* {
  box-sizing: border-box;
}

.container {
  margin-left: auto;
  margin-right: auto;
  padding-left: 10px;
  padding-right: 10px;
  max-width: 700px;
  box-sizing: border-box;
  text-align:;
}

h1, h2, h3, h4, h5, h6 {
  margin-top:0px;
}

</style>
