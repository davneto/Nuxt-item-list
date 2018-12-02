<template>

  <section class="breadcrumb_wrapper">
    <ul class="breadcrumb breadcrumb_ul">
      <li v-for="(section) in sections">
        <!-- <nuxt-link :to="'/items/' + id" >{{ section.name }}</nuxt-link> -->
        <nuxt-link v-if="section.url !== ''" :to="section.url" >{{ section.name }}</nuxt-link>
        <span v-if="section.url === ''">{{ section.name }}</span>
      </li>
    </ul>
  </section>


</template>

<script>


export default {
  props: ['sections'],
  // data : function () {
  //   return {
  //     sections: [
  //       {name: 'Items', url: '/'},
  //       //{name: 'item 1', url: '/items/1'}
  //       {name: 'Item 1', url: ''}
  //     ]
  //   }
  // }
}
</script>

<style scoped>

  .breadcrumb_wrapper {
    width: 100%;
    /* padding-bottom: $vertical-rythm-space-component; */
  }

  .breadcrumb_ul {
    white-space: nowrap;
    list-style: "»";
    padding-left: 0;
  }

  .breadcrumb_ul > li {
    display: inline-block;
  }

  .breadcrumb_ul > li:not(:first-child)::before {
    content: "» ";
  }

</style>
