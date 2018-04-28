<template>
  <section class="section orders__section">
      <div class="container">
          <h2 class="title2">Как осуществляется заказ</h2>
          <div class="orders">
              <div class="order" v-for="(order,index) in orders" :key="index">
                  <div class="order__icon">
                      <img :src="order.icon" :alt="order.title" class="order__img">
                  </div>
                  <div class="order__title">
                      {{order.title}}
                  </div>
                  <div class="order__text">
                     {{order.text}}
                  </div>
              </div>
          </div>
      </div>
  </section>
</template>

<script>
export default {
  data(){
      return {
          orders: [
              {
                  icon: require('../assets/images/order-icon.png'),
                  title:'Заявка',
                  text:'Вы отправляете заявку через форму или звоните'
              },
              {
                  icon: require('../assets/images/order-icon2.png'),
                  title:'Контакт',
                  text:'Наш менеджер звонит вам и консультирует по выбору подходящего вам изделия'
              },
                            {
                  icon: require('../assets/images/order-icon3.png'),
                  title:'Вызов замерщика',
                  text:'Выезд замерщика в удобное для Вас время'
              },
                            {
                  icon: require('../assets/images/order-icon4.png'),
                  title:'Расчет',
                  text:'Мы выполняем расчет изделий согласно замеру'
              },
                            {
                  icon: require('../assets/images/order-icon5.png'),
                  title:'Изготовление',
                  text:'Срок изготовления от 3 х дней'
              },
                            {
                  icon: require('../assets/images/order-icon6.png'),
                  title:'Монтаж',
                  text:'Монтаж в течении 1 рабочего дня'
              }
              
          ]
      };
  }
}
</script>

<style lang="scss" scoped>
    .orders{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        &__section{
            padding-bottom: 0;
        }
    }
    .order{
        width: 300px;
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-bottom: 100px;
        &:first-child{
            position: relative;
            &:after{
                content:'';
                display:block;
                height: 5px;
                width: 100vw;
                position: absolute;
                top:45px;
                z-index: -1;
                left: 220px;
                background: url('../assets/images/dots.png');
            }
        }
        &:last-child{
            position: relative;
            &:before{
                content:'';
                display:block;
                height: 5px;
                width: 100vw;
                position: absolute;
                top:45px;
                z-index: -1;
                right: 220px;
                background: url('../assets/images/dots.png');
            }
        }
        &__icon{
            width: 100px;
            height: 100px;
            border-radius: 50%;
            border:2px solid #e0eee0;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 30px;
            background: #fff;
        }
        &__title{
           font-weight: bold;
           color:#3c4d43;
           font-size:20px;
           margin-bottom: 30px;
        }
        &__text{
            text-align: center;
            color:#9c9c9c;
            font-size:16px;
            line-height: 2;
        }
    }
</style>
