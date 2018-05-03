<template>
<div class="flex-wrapper">
  <div class="flex-content">
    <section class="section single-product">
          <div class="container">
            <h1 class="title2 single-product__title">{{title}}</h1>
            <a href="#" class="link">Просмотреть каталог</a>
            <img class="single-product__image" src="http://www.domokna.ru/image/data/category/vertikalnye-zhaljuzi/vertic-jaluze.jpg" alt="">
            <p class="single-product__text">Красиво и стильно оформить окна бывает очень не просто, это известно всем, кто хоть раз участвовал в ремонте квартиры, переезжал на новое место жительства, оформлял офис. Проблема, как правило, состоит в дилемме – либо эффектный вид, либо функциональность, при этом появляется нежелание выбирать что-то одно. Вертикальные жалюзи помогут создать гармоничный общий вид комнаты, органично вписаться в стиль и цветовое решение интерьера, придать ему необходимую строгость или мягкость, обеспечив при этом максимальную защиту от солнца и пыли.
            </p>
            <p class="single-product__text">
              Каталог компании составляет более 300 тканей различных фактур, представляем материал жалюзи из натуральной ткани (Лен) или из 100% полиэстера. Все ткани вертикальных жалюзи имеют ширину ламели 89 мм, но различаются по плотности и цвету, есть однотонные и с рисунком, гладкие и рельефные — жаккардовые (Жаккард, Венера, Офелия). По свето-пропусканию различаются в широком диапазоне от почти прозрачных (Скрин, Шикатан) до полностью непрозрачных — блэкауты (Офис Б.А., Сиде Б.А., Жемчуг Б.А., Жаккард Б.А., Замша).
            </p>
          </div>
    </section>
  </div>
</div>
</template>
<script>
export default {
  asyncData(context) {
      return context.app.$storyapi
      .get('cdn/stories/products/' + context.params.postId, {
          version: 'draft'
      })
      .then(res => {
          return {
            //   blok: res.data.story.content,
              image: res.data.story.content.image,
              title: res.data.story.content.title,
              text: res.data.story.content.text,
              price: res.data.story.content.price,
          };
          
      });
  },
//   mounted(){
//       this.$storyblok.init()
//       this.$storyblok.on('change', () => {
//           location.reload(true);
//       });
//   }
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
