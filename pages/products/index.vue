<template>
  <section class="section">
    <div class="container">
      <h1 class="title1">Продукция</h1>
          <div class="products">
            <nuxt-link  v-for="(product,index) in products" :key="index" :to="'products/'+product.fields.slug" class="product">
              <div class="product__title">
                {{product.fields.name}}
              </div>
              <div class="product__img" :style="{backgroundImage: 'url(' + product.fields.main_image.fields.file.url + ')'}"></div>
              <div class="product__price">
                {{product.fields.price}}
              </div>
            </nuxt-link>
          </div>
    </div>
  </section>
</template>

<script>

import client from '~/plugins/contentful';

export default {
  asyncData({ params }) {
    return client
      .getEntries({
        content_type: 'product',
        order: '-sys.createdAt',
      })
      .then(entries => {
        return { products: entries.items };
      })
      .catch(e => console.log(e));
  },
}
</script>
