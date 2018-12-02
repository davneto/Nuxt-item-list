<template>
  <section>

    <Breadcrumb :sections="get_breadcrumb_sections" class="container"></Breadcrumb>

    <main class="container">
      <h1>{{ items.title }}</h1>
      <img class="image" :src="'https://source.unsplash.com/random?random=' + random_int_range(1, 10000000) + '.' + random_int_range(1, 10000000)" alt="item image" />
      <p class="description">{{ items.description }}</p>
    </main>

  </section>
</template>

<script>

import Breadcrumb from '@/components/Breadcrumb';

export default {
  components: {
    Breadcrumb
  },
  data : function () {
    return {
      breadcrumb_sections: [],
      items: []
    }
  },
  computed: {
    get_breadcrumb_sections: function() {
      return [
      { name: 'Items', url: '/' },
      { name: this.items.title , url: ''}
      ];
    }
  },
  methods: {
    random_int_range: function(min, max) {
      return Math.floor((Math.random() * (max - min)) + min);
    }
  },
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(
        () => {
          resolve({
            items: [
              {
                id: "1",
                title: "Item 1",
                description: "An amazing item!"
              },
              {
                id: "2",
                title: "Item 2",
                description: "Another amazing item!"
              },
              {
                id: "3",
                title: "Item 3",
                description: "Yet another!!!"
              }
            ].find(el => el.id === context.params.id)
          });
        },0); //timeout
    }); //Promise
  } //asyncData
}
</script>

<style scoped>


  main {
    /*border: 1px solid #ccc;*/
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 10px;
    /*margin: 10px;*/
  }

  .image {
    max-width:500px;
    max-height:70vh;

  }


</style>
