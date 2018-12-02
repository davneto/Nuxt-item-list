<template>
  <main>

    <Breadcrumb :sections="breadcrumb_sections" class="container"></Breadcrumb>

    <section class="container item-list">

      <Item id="1" title="Item 1" description="An amazing item!" />
      <Item id="2" title="Item 2" description="One more amazing item!!" />
      <Item id="3" title="Item 3" description="Yet another!!!" />

    </section>

  </main>
</template>

<script>

import Item from '@/components/Item'
import Breadcrumb from '@/components/Breadcrumb';

export default {
  components: {
    Item,
    Breadcrumb
  },
  data : function () {
    return {
      breadcrumb_sections: [{name: 'Items', url: ''}]
    }
  },
  methods: {
    random_int_range: function(min, max) {
      return Math.floor((Math.random() * (max - min)) + min);
    }
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(
        () => {
          resolve({
            items: [
              {
                id: "1",
                title: "",
                description: "An amazing item!"
              },
              {
                id: "2",
                title: "",
                description: "Another amazing item!"
              },
              {
                id: "3",
                title: "",
                description: "+1"
              }
            ]
          });
        },0); //timeout
    }); //Promise
  } //asyncData
};
</script>

<style scoped>

  .item-list {
    display: flex;
    justify-content: center;
    align-content: center;
  }

</style>
