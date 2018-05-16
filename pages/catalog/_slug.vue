<template>
  <div class="section">
    <div class="container">
      <h1 class="title1">{{category.fields.title}}</h1>
        <p v-html="$md.render(category.fields.content)"></p>
        <br>
        <hr>
        <br>
        <div class="category-grid">
          <nuxt-link  v-for="(item,index) in category.fields.products" :key="index" :to="'/'+item.fields.slug" class="category">
              <div class="category__title">
                {{item.fields.name}}
              </div>
              <div class="category__img" :style="{backgroundImage: 'url(' + item.fields.main_image.fields.file.url + ')'}"></div>
              <div class="category__price">
                {{item.fields.price}}
              </div>
          </nuxt-link>
        </div>
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
        'content_type': 'category',
        'fields.slug': params.slug,
      })
      .then(entries => {
        return { category: entries.items[0] };
      })
      .catch(e => console.log(e));
  },
  head() {
    return {
      title: this.category.fields.title,
    };
  }
};
</script>

<style lang="scss" scoped>
  .single-product{
    &__text{
      line-height: 20px;
      font-size:14px;
      margin-bottom: 15px;
    }
    &__image{
      float: right;
      width: 30%;
      margin-left: 15px;
      margin-bottom: 15px;
    }
  }
</style>
