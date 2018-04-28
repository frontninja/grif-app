<template>
  <section class="section">
    <div class="container">
      <h1 class="title1">Продукция</h1>
      <div class="products">
        <nuxt-link  v-for="product in products" :key="product.id" :to="'products/'+product.id" class="product">
          <div class="product__title">
            {{product.title}}
          </div>
          <div class="product__img" :style="{backgroundImage: 'url(' + product.url + ')'}"></div>
          <div class="product__price">
            {{product.price}}
          </div>
        </nuxt-link>
      </div>
    </div>
  </section>
</template>

<script>
export default {
    asyncData(context) {
      return context.app.$storyapi
        .get('cdn/stories', {
          version: 'draft',
          starts_with: 'products/'
        }).then(res => {
          return {
            products: res.data.stories.map(bp => {
              return {
                // blok: bp.content,
                id: bp.slug,
                title: bp.content.title,
                url: bp.content.preview_image,
                price: bp.content.price,
              }
            })
          };
        });
    }
}
</script>
