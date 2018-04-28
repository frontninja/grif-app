<template>
  <header class="header">
    <div class="topline">
      <div class="container topline__container">
          <nuxt-link to="/" class="logo topline__logo">
            <img src="../../assets/images/main-logo.png" alt="Салон Гриф жалюзи">
        </nuxt-link>
        <nav class="navigation">
          <i class="fa fa-bars navigation__trigger" aria-hidden="true"></i>
          <ul class="navigation__ul">
            <nuxt-link to="/products" tag="li" class="navigation__li">
            <a class="navigation__link">Продукция</a>
            </nuxt-link>
            <nuxt-link to="/about" tag="li" class="navigation__li">
            <a class="navigation__link">О нас</a>
            </nuxt-link>
                        <nuxt-link to="/gallery" tag="li" class="navigation__li">
            <a class="navigation__link">Галерея</a>
            </nuxt-link>
                        <nuxt-link to="/catalog" tag="li" class="navigation__li">
            <a class="navigation__link">Каталог тканей</a>
            </nuxt-link>
                        <nuxt-link to="/contacts" tag="li" class="navigation__li">
            <a class="navigation__link">Контакты</a>
            </nuxt-link>
          </ul>
        </nav>
        <div class="topline__right">
          <div class="info">
            <span class="info__adress">г. Ялта, ул. Киевская 60</span>
            <div class="info__bottom">
              <span class="info__span">Офис №4</span>
              <span class="info__span">пн-пт: 9
                <span class="ultrasmall">00</span> - 17
                <span class="ultrasmall">00</span>
              </span>
            </div>
          </div>
          <button class="button button_main" data-text="Обратный звонок">+7 978 091 99 98</button>
        </div>
      </div>
    </div>
  </header>
</template>

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
      margin-right: 30px;
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
            background: #007a42;;
            z-index: 1;
            padding: 15px 0;
            width: 250px;
            &.active{
                left: 0;
            }
        }
        &__li{
            height: initial;
            border-left: none;
            &+&{
                border-top:1px solid #fff;
            }
            &:last-child{
                border-right: none;
            }
        }
        &__link{
            height: 40px;
            font-size: 20px;
            color:#fff;
            justify-content: center;
        }
    }
}

</style>
