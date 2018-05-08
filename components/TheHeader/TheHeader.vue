<template>
  <header class="header">
    <div :class="'overlay '+ activeNav" @click="activeNav = ''"></div>
    <div class="topline">
      <div class="container topline__container">
          <nuxt-link to="/" class="logo topline__logo">
            <img src="../../assets/images/main-logo.png" alt="Салон Гриф жалюзи">
        </nuxt-link>
        <nav class="navigation">
          <i class="icon-menu navigation__trigger" aria-hidden="true" @click="activeNav = 'active'"></i>
          <ul :class="'navigation__ul ' + activeNav" @click="activeNav = ''">
            <nuxt-link :to="item.url" tag="li" class="navigation__li" v-for="(item,index) in menu" :key="index">
                <a class="navigation__link" >{{item.text}}</a>
            </nuxt-link>
            <li class="navigation__li navigation__li_small">
                {{adres}}
            </li>
            <li class="navigation__li navigation__li_small">
                {{phone}}
            </li>
          </ul>
        </nav>
        <div class="topline__right">
          <div class="info">
            <span class="info__adress"><i class="icon-location-pin info__icon"></i>{{adres}}</span>
            <div class="info__bottom">
              <span class="info__span">Офис №4</span>
              <span class="info__span">пн-пт: 9
                <span class="ultrasmall">00</span> - 17
                <span class="ultrasmall">00</span>
              </span>
            </div>
          </div>
          <button class="button button_main topline__phone" data-text="Обратный звонок" @click="$toast.success('hello billo')"><i class="icon-phone info__icon"></i>{{phone}}</button>
        </div>
      </div>
    </div>
  </header>
</template>

<script>


export default {
    data(){
        return {
            activeNav: '',
            adres:'г. Ялта, ул. Киевская 60',
            phone: '+7 978 091 99 98',
            menu: [
                {
                    text: 'Каталог',
                    url: '/catalog'
                },
                                {
                    text: 'О нас',
                    url: '/about'
                },
                                {
                    text: 'Галерея',
                    url: '/gallery'
                },
                                {
                    text: 'Контакты',
                    url: '/contacts'
                }
            ]
        }
    }
}

</script>

<style lang="scss">
  .topline {
    background: #fafafa;
    height: 90px;
    &__container {
      height: 100%;
      display: flex;
      align-items: center;
    }
    &__logo {
      margin-right: 15px;
    }
    &__right {
      margin-left: auto;
      display: flex;
      align-items: center;
    }
  }
  .navigation{
    height: 100%;
    &__trigger{
        display: none;
    }
    &__ul{
        height: 100%;
        display:flex;
    }
    &__li{
        height: 100%;
        list-style: none;
        // border-left:1px solid #eeeeee;
        &:last-child{
            // border-right:1px solid #eeeeee
        }
        &_small{
            display: none;
            color: #fff;
            text-align: center;
            font-size: 18px;
            border-top: 1px solid #ffffff82;
            padding: 15px;
            &+&{
                border-top:none;
            }
        }
        &.nuxt-link-active{
            .navigation__link{
                border-bottom:5px solid darken(#00ad5d,10%);
                color:#00ad5d;
            }
        }
    }
    &__link{
        height: 100%;
        display: flex;
        align-items: center;
        font-size: 18px;
        color: #2b2b2b;
        text-decoration: none;
        background-color: transparent;
        padding: 0 15px;
        transition:background-color .3s ease-in-out,border .3s ease-in-out,color .3s ease-in-out;
        border-bottom:0px solid darken(#00ad5d,10%);
        &:hover{
            background-color:#e7e7e7;
        }
    }
}
.info{
    background: url('../../assets/images/adress-bg.png') no-repeat;
    background-position-x: 44%;
    background-position-y:center;
    background-size: contain;
    height: 55px;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    position: relative;
    top:-10px;
    margin-right: 30px;
    &__icon{
        display: none;
        color:#00ad5d;
        margin-right: 5px;
    }
    &__adress{
        font-size: 20px;
    }
    &__span{
        font-size:14px;
        color:#484848;
        display: flex;
        align-items: flex-start;
    }
    &__bottom{
        display: flex;
        justify-content: space-between;
    }
}
.ultrasmall{
    font-size: 8px;
    position: relative;
    top: 2px;
    margin: 0 1px;
}

@media (max-width:1200px){
    
    .overlay{
        transition: background .3s ease-in-out;
        background: transparent;
        &.active{
        position: absolute;
        top:0;
        left: 0;
        right: 0;
        bottom: 0;
        background: rgba(#000000,0.25);
        z-index: 100;
        }
    }
    .navigation{
        height: 100%;
        &__trigger{
            display: flex;
            height: 100%;
            align-items: center;
            font-size: 50px;
            padding: 0 15px;
            cursor: pointer;
        }
        &__ul{
            display: flex;
            flex-direction: column;
            position: fixed;
            left: -100%;
            top: 0;
            height: 100vh;
            background: #007a42;
            background: linear-gradient(bottom right, #00562e, #00c76b); /*Standard*/
            z-index: 101;
            padding: 15px 0;
            width: 250px;
            transition: left .3s ease-in-out;
            &.active{
                left: 0;
            }
        }
        &__li{
            height: initial;
            border-left: none;
            &:last-child{
                border-right: none;
            }
            &.nuxt-link-active{
                background: rgba(#000,0.15);
            .navigation__link{
                border-bottom:none;
                color:#fff;
            }
        }
        }
        &__link{
            height: 40px;
            font-size: 20px;
            color:#fff;
            justify-content: center;
            text-shadow: 2px 2px 11px rgba(0, 0, 0, .5);
        }
    }
}

@media(max-width: 692px){
    .info{
        &__icon{
            display: inline-block;
        }
        background: none;
            margin-right: 0;
            top:0;
            font-size: 18px;
            height: initial;
            margin-bottom: 15px;
            &__bottom{
                display: none;
            }
    }
    .topline{
        &__right{
            flex-direction: column;
        }
        &__phone{
            background: none;
            height: initial;
            padding: 0;
            color:#000;
        }
    }
}

@media(max-width: 490px){
    .topline{
        &__container{
            justify-content: space-between;
        }
        &__logo{
            order:2;
            margin-right: 0;
        }
        &__right{
            display: none;
        }
    }
    .navigation__li_small{
        display: inline-block;
    }
}

</style>
