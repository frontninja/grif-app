<template>
  <div class="section">
    <div class="container flex-container">
      <div class="column flex-column">
        <a href="javascript:history.go(-1)" class="go-back">
          <i class="icon-arrow-left go-back__icon"></i> Назад</a>
        <h1 class="single-product__title">
          {{product.fields.name}}
        </h1>
        <div class="single-product__content">
          <div class="single-product__text">
            <p>Вертикальные тканевые жалюзи позволяют создать неповторимые дизайнерские композиции, предоставляя все возможности цвета для самой неутомимой фантазии. Специальная антистатическая и пылеотталкивающая обработка гарантирует долговечность тканевых вертикальных жалюзи.

Каталог компании составляет более 300 тканей различных фактур, представляем материал жалюзи из натуральной ткани (Лен) или из 100% полиэстера. Все ткани вертикальных жалюзи имеют ширину ламели 89 мм, но различаются по плотности и цвету, есть однотонные и с рисунком, гладкие и рельефные — жаккардовые (Жаккард, Венера, Офелия). По свето-пропусканию различаются в широком диапазоне от почти прозрачных (Скрин, Шикатан) до полностью непрозрачных — блэкауты (Офис Б.А., Сиде Б.А., Жемчуг Б.А., Жаккард Б.А., Замша).</p>
          </div>
          <a href="#" class="single-product__link"><i class="icon-link"></i> Ссылка на каталог</a>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
  import client from '~/plugins/contentful';
  export default {
    asyncData({
      params,
      error,
      payload
    }) {
      if (payload) return {
        product: payload
      };
      return client
        .getEntries({
          'content_type': 'product',
          'fields.slug': params.slug,
        })
        .then(entries => {
          return {
            product: entries.items[0]
          };
        })
        .catch(e => console.log(e));
    },
    head() {
      return {
        title: this.product.fields.name,
      };
    }
  };

</script>

<style lang="scss" scoped>
  .single-product {
    &__title{
      font-size: 26px;
      color:#111;
      margin-bottom: 15px;
    }
    &__content{
      margin-bottom: 30px;
    }
    &__text {
      line-height: 20px;
      font-size: 14px;
      margin-bottom: 15px;
      color:rgba(0, 0, 0, .8);
    }
    &__link{
      color:#00ad5d;
      font-size:18px;
      text-decoration: none;
      display: flex;
      align-items: baseline;
      .icon-link{
        margin-right: 7px;
      }
      &:hover{
        color:darken(#00ad5d,10%);
      }
    }
    &__image {
      float: right;
      width: 30%;
      margin-left: 15px;
      margin-bottom: 15px;
    }
  }

  .go-back {
    font-size: 14px;
    color: rgba(0, 0, 0, .5);
    text-transform: uppercase;
    text-decoration: none;
    display: flex;
    align-items: center;
    transition: .3s ease-in-out;
    margin-bottom: 30px;
    &:hover{
      color: rgba(0, 0, 0, .7);
    }
  }

</style>
