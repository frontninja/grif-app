<template>
  <div class="wrapper">
    <div class="content">
        <TheHeader/>
        <div class="container container_sidebar">
            <div class="sidebar">
                <side />
            </div>
            <div class="main">
                <nuxt/>
            </div>
        </div>
    </div>
    <TheFooter/>
  </div>
</template>
<script>
import TheHeader from '@/components/TheHeader/TheHeader.vue';
import TheFooter from '@/components/TheFooter/TheFooter.vue';
import side from '@/components/side.vue';

import client from '~/plugins/contentful';

export default {
   components: {
    TheHeader,
    TheFooter,
    side
  },
}
</script>



<style lang="scss">
html
{
      font-family: 'Noto Sans', sans-serif;
      font-size: 14px;
      line-height: 1.2;
      color:#000000;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}
*, *:before, *:after
{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
html,
body,
#__nuxt,
#__layout
 {
  height: 100%;
}
    .container_sidebar{
        display: flex;
    }
    .sidebar{
        width: 30%;
        padding: 100px 0;
    }
    .main{
        width: 70%;
    }
.wrapper {
  display: flex;
  flex-direction: column;
  height: 100%;
  width: 100%;
  overflow-x: hidden;
}
.content {
  flex: 1 0 auto;
}
.footer {
  flex: 0 0 auto;
}
.container{
    width: 1200px;
    padding: 0 15px;
    margin: 0 auto;
}
.section{
    padding: 100px 0;
    &_dark{
        background-color:#465046;
        background: linear-gradient(135deg, rgba(113,143,89,1) 0%, rgba(70,80,70,1) 100%);
        color:#fff;
    }
    &_lightgreen{
        background-color:#dbebdb;
        background: linear-gradient(135deg, #ecf5ec 0%, #dbebdb 100%);
    }
}
.input{
    height: 60px;
    font-size: 18px;
    line-height: 60px;
    border-radius: 3px;
    border:1px solid #dbe4eb;
    padding: 0 20px;
    transition: border .3s ease-in-out;
    width: 100%;
    &+&{
        margin-left: 30px;
    }
    &:placeholder{
        color:#b2c1cc;
        font-weight: normal;
        font-family: 'Noto Sans', sans-serif;
    }
    &::-webkit-input-placeholder{
        color:#b2c1cc;
        font-weight: normal;
        font-family: 'Noto Sans', sans-serif;
    }
    &:focus{
        outline: none;
        border:#00ad5d 1px solid;
    }
    &__box{
        display: flex;
        margin-bottom: 30px;
    }
}
.textarea{
    font-size: 18px;
    line-height: 24px;
    width: 100%;
    padding: 14px 20px;
            border-radius: 3px;
    border:1px solid #dbe4eb;

    transition: border .3s ease-in-out;
    &:placeholder{
        color:#b2c1cc;
        font-weight: normal;
        font-family: 'Noto Sans', sans-serif;
    }
    &::-webkit-input-placeholder{
        color:#b2c1cc;
        font-weight: normal;
        font-family: 'Noto Sans', sans-serif;
    }
    &:focus{
        outline: none;
        border:#00ad5d 1px solid;
    }
}
.button{
    height: 60px;
    border: none;
    background: #00ad5d;
    background: linear-gradient(bottom right, #00ad5d, #00d070); /*Standard*/
    padding: 0 30px;
    font-size: 18px;
    color:#fff;
    border-radius: 3px;
    cursor: pointer;
    transition: .3s ease-in-out background-color;
    &+&{
        margin-left: 10px;
    }
    &:hover{
        background: lighten(#00ad5d,5%);
        background: linear-gradient(bottom right,  lighten(#00ad5d,5%), lighten(#00d070,5%)); /*Standard*/
    }
    &:focus{
        outline: none;
        background: darken(#00ad5d,5%);
        background: linear-gradient(bottom right,  darken(#00ad5d,5%), darken(#00d070,5%)); /*Standard*/
    }
    &_transparent{
        background-color: transparent;
        border:2px solid #00ad5d;
    }
}
.title1 {
    color:#363636;
    font-size:48px;
    font-weight: bold;
    margin-bottom: 50px;
}
.title2{
    color:#363636;
    font-size:36px;
    font-weight: bold;
    margin-bottom: 50px;
}
.link{
    color:#00ad5d;
    transition: color .3s ease-in-out;
    &:hover{
        color:darken(#00ad5d,10%);
    }
}

@media(max-width:1199px){
.container{
    width: 100%;
}
}
@media(max-width: 600px){
    .title2{
        font-size:24px;
        text-align: center;
    }
}
</style>
