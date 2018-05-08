<template>
  <div class="section">
    <div class="container">
  <h1>{{product.fields.name}}</h1>
  <nuxt-link to="/gallery">gallery</nuxt-link>
    </div>
  </div>
</template>

<script>
import client from '~/plugins/contentful';
export default {
  asyncData({ params, error, payload }) {
    if (payload) return { category: payload };
    return client
      .getEntries({
        content_type: 'category',
        'fields.slug': params.slug,
      })
      .then(entries => {
        return { product: entries.items[0].fields.products[0] };
      })
      .catch(e => console.log(e));
  },
  // head() {
  //   return {
  //     title: this.product.fields.name,
  //   };
  // },
};
</script>