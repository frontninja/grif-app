<template>
  <ul class="sidebar__ul">
    <li class="sidebar__title">Каталог</li>
    <!-- <nuxt-link v-for="(item,index) in menu" :key="index" :to="item.link" tag="li" class="sidebar__li">
      <a class="sidebar__link">{{item.title}}</a>
      <ul class="sidebar__subul">
        <nuxt-link v-for="(subitem,index) in item.products" :key="index" :to="subitem.link" tag="li" class="sidebar__subli">
          <a class="sidebar__sublink">{{subitem.title}}</a>
        </nuxt-link>
      </ul>
      </nuxt-link> -->
  </ul>
</template>

<script>


export default {
  // data(){
  //   return {
  //     menu: [
  //       {
  //         title:'Жалюзи вертикальные',
  //         link:'/catalog/zhalyuzi-vertikalnye',
  //         products: [
  //           {
  //             title:'Тканевые',
  //             link:'/catalog/zhalyuzi-vertikalnye/tkanevye-vertikalnye-zhalyuzi'
  //           }
  //         ]
  //       },
  //     ]
  //   }
  // }
}
</script>

<style lang="scss" scoped>
  .sidebar{
    .nuxt-link-active{
      a{
        color:#004122;
      }
    }
    &__title{
      list-style: none;
      font-size: 24px;
      color:rgb(32, 32, 32);
      margin-bottom: 30px;
      font-weight: bold;
    }
    &__li{
      list-style: none;
    }
    &__link{
      font-size: 20px;
      color:#00ad5d;
      text-decoration: none;
    }
    &__ul{
      padding: 15px;
      border:1px solid #00ad5d;
      border-radius: 3px;
      margin-right: 15px;
    }
    &__subul{
      margin-top: 10px;
    }
    &__subli{
      list-style: none;
    }
    &__sublink{
      font-size: 16px;
      color:#5bc996;
      text-decoration: none;
      
    }
  }
</style>
