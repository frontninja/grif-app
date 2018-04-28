<template>
<div class="flex-wrapper">
  <div class="flex-content">
    <section class="section">
          <div class="container">
        <div class="product-single">
          <h1 class="title2">{{title}}</h1>
          <p class="product-single__subtitle">{{price}}</p>
          <img :src="image" :alt="title">
          <p class="product-single__text">{{text}}</p>
        </div>
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