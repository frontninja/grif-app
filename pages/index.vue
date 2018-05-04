<template>
  <div class="flex-wrapper">
    <seo />
    <div class="flex-content">
      <!-- <modal /> -->
      <Screen />
      <section class="section">
        <div class="container">
          <h2 class="title2">Мы предоставляем большой выбор продукции</h2>
          <!-- <div class="products">
            <nuxt-link  v-for="product in products" :key="product.id" :to="'products/'+product.id" class="product">
              <div class="product__title">
                {{product.title}}
              </div>
              <div class="product__img" :style="{backgroundImage: 'url(' + product.url + ')'}"></div>
              <div class="product__price">
                {{product.price}}
              </div>
            </nuxt-link>
          </div> -->
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
          <div class="products__line">
            <nuxt-link to="/products" class="products__all">Вся продукция</nuxt-link>
          </div>
        </div>
      </section>

      <!-- Pr section -->
      <pr />

      <!-- Order section -->
      <order />
    </div>
  </div>

</template>

<script>
  import Screen from '@/components/Screen.vue';
  import pr from '@/components/pr.vue';
  import order from '@/components/order.vue';
  import seo from '@/components/seo.vue';

  import client from '~/plugins/contentful';

  export default {
    components: {
      Screen,
      pr,
      order,
      seo,
    },
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
  head: {
    title: 'Latest Posts',
  },
    // asyncData(context) {
    //   return context.app.$storyapi
    //     .get('cdn/stories', {
    //       version: 'draft',
    //       starts_with: 'products/'
    //     }).then(res => {
    //       return {
    //         products: res.data.stories.map(bp => {
    //           return {
    //             id: bp.slug,
    //             title: bp.content.title,
    //             url: bp.content.preview_image,
    //             price: bp.content.price,
    //           }
    //         })
    //       };
    //     });
    // }
  }

</script>

<style lang="scss">
  .products {
    display: flex;
    // justify-content: space-around;
    flex-wrap: wrap;
    position: relative;
    margin: 0 -15px;
    &__all {
      display: inline-block;
      color: #00ad5d;
      font-size: 18px;
      height: 40px;
      line-height: 35px;
      text-decoration: none;
      padding: 0 25px;
      border-radius: 3px;
      border: 2px solid #dbebdb;
      white-space: nowrap;
      margin: 0 20px;
      transition: border .3s ease-in-out;
      &:hover {
        border: 2px solid #00ad5d;
      }
    }
    &__line {
      display: flex;
      align-items: center;
      &:before {
        content: '';
        display: block;
        height: 2px;
        width: 100%;
        background: #dbebdb;
      }
      &:after {
        content: '';
        display: block;
        width: 100%;
        height: 2px;
        background: #dbebdb;
      }
    }
  }

  .product {
    text-decoration: none;
    color: #111;
    width: 270px;
    display: flex;
    flex-direction: column;
    position: relative;
    margin: 0 15px;
    margin-bottom: 30px;
    &__title {
      font-size: 16px;
      font-weight: normal;
      padding-top: 7px;
      margin-bottom: 7px;
      border-top: 1px solid #c9c9c9;
      border-right: 1px solid #c9c9c9;
      color: #00c76b;
      text-decoration: underline;
    }
    &__img {
      width: 100%;
      height: 170px;
      background-size: cover;
      ;
    }
    &__price {
    position: absolute;
    /* top: 104px; */
    /* left: 182px; */
    right: 0;
    bottom: 0px;
    /* -webkit-transform: rotate(90deg); */
    /* transform: rotate(90deg); */
    white-space: nowrap;
    font-size: 14px;
    /* width: 160px; */
    color: #fff;
    text-align: center;
    padding: 2px 5px;
    width: 100%;
    justify-content: center;
    align-items: flex-end;
    display: flex;
    height: 170px;
    padding-bottom: 7px;
    background: linear-gradient(to bottom, rgba(255,255,255,0) 0%, rgb(0, 88, 11) 100%);
    /* background: #009651; */
    }
  }

  .flex-wrapper {
    display: flex;
    flex-direction: column;
  }

  .seo {
    order: 2;
  }

</style>
