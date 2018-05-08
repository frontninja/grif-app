<template>
  <ul>
    <nuxt-link v-for="(item,index) in menu" :key="index" :to="item.link" tag="li">
      <a>{{item.title}}</a>
      <ul>
        <nuxt-link v-for="(subitem,index) in item.products" :key="index" :to="subitem.link" tag="li">
          <a>{{subitem.title}}</a>
        </nuxt-link>
      </ul>
      </nuxt-link>
  </ul>
</template>

<script>
export default {
  data(){
    return {
      menu: [
        {
          title:'Жалюзи вертикальные',
          link:'/catalog/zhalyuzi-vertikalnye',
          products: [
            {
              title:'Тканевые',
              link:'/catalog/zhalyuzi-vertikalnye/tkanevye-vertikalnye-zhalyuzi'
            }
          ]
        },
      ]
    }
  }
}
</script>
