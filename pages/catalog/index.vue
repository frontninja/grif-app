<template>
  <div class="section">
    <div class="container">
        <h1 class="title1">Каталог</h1>
        <div class="category-grid">
          <nuxt-link  v-for="(category,index) in categories" :key="index" :to="'catalog/'+category.fields.slug" class="category">
              <div class="category__img" :style="{backgroundImage: 'url(' + category.fields.image.fields.file.url + ')'}"></div>
              <div class="category__title">
                {{category.fields.title}}
              </div>
              <div class="category__price">
                {{category.fields.price}}
              </div>
          </nuxt-link>
        </div>
    </div>
  </div>
</template>

<script>

import client from '~/plugins/contentful';

export default {
  asyncData({ params }) {
    return client
      .getEntries({
        content_type: 'category',
        order: '-sys.createdAt',
      })
      .then(entries => {
        return { categories: entries.items };
      })
      .catch(e => console.log(e));
  },
}
</script>

<style lang="scss">

.category-grid {
    display: flex;
    flex-wrap: wrap;
    margin: 0 -15px;
}

  .category {
    color: #111;
    width: 270px;
    display: flex;
    flex-direction: column;
    margin: 0 15px;
    margin-bottom: 30px;
    text-decoration: none;
    text-align: center;
    border-radius: 2px;
    background-color:#fff;
    box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
    transition: all 0.3s cubic-bezier(.25,.8,.25,1);
    &:hover{
        box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
    }
    &__title {
      font-size:16px;
      font-weight: bold;
      color:#3c4d3c;
      margin-bottom: 15px;
      text-transform: uppercase;
    }
    &__img {
      width: 100%;
      height: 170px;
      background-size: cover;
      margin-bottom: 15px;
      opacity: 1;
      transition: opacity .3s ease-in-out;
    }
    &__price {
      font-size:24px;
      font-weight: bold;
      color:#3c4d3c;
      margin-bottom: 15px;
    }
  }

</style>

