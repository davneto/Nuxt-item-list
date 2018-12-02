<template>

  <nuxt-link :to="'/items/' + id" >
    <article class="item">
      <img class="item-image" :src="'https://source.unsplash.com/random'" alt="item image" />
      <h1 class="title">{{this.title}}</h1>
      <p class="description">{{this.description}}</p>
    </article>
  </nuxt-link>

</template>

<script>

export default {
  props: ["id", "title", "description"],
  methods: {
    random_int_range: function(min, max) {
      return Math.floor((Math.random() * (max - min)) + min);
    }
  }
}
</script>

<style scoped>

  .item {
    border: 1px solid #ccc;
    width:300px;
    padding: 10px;
    margin: 10px;
  }

  .item-image {
    width:100%;
  }

</style>
