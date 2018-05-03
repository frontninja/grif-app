<template>
  <div class="section section_dark">
    <div class="container prs">
      <div class="pr" v-for="(pr,index) in prs" :key="index">
        <div class="pr__icon"></div>
        <div class="pr__content">
          <p class="pr__title">
            {{pr.title}}
          </p>
          <p class="pr__subtitle">
            {{pr.subtitle}}
          </p>
        </div>
      </div>
    </div>

  </div>
</template>
<script>
  export default {
    data() {
      return {
        prs: [{
            title: 'Профессионализм',
            subtitle: '19 лет работы на рынке'
          },
          {
            title: 'Качество',
            subtitle: 'Более 10 тысяч довольных заказчиков'
          },
          {
            title: 'Удобство',
            subtitle: 'Изготовление по индивидуальным размерам'
          },
        ]
      };
    }
  }

</script>

<style lang="scss" scoped>
  .prs {
    display: flex;
    justify-content: space-around;
  }

  .pr {
    display: flex;
    width: 370px;
    &__icon {
      width: 35px;
      height: 35px;
      display: block;
      background: url('../assets/images/check-icon.png') no-repeat;
      margin-right: 30px;
      background-size: contain;
    }
    &__content {
      padding-top: 5px;
    }
    &__title {
      font-weight: bold;
      font-size: 20px;
      margin-bottom: 15px;
    }
    &__subtitle {
      font-size: 18px;
      color: #d8d8d8;
    }
  }

  @media(max-width:951px){
    .pr {
      flex-direction: column;
      padding: 0 10px;
    }
  }
  @media(max-width:615px){
    .prs {
      flex-direction: column;
    }
    .pr{
      align-items: center;
      width: 100%;
      flex-direction: row;
      &__icon{
        flex-shrink: 0;
      }
      &+&{
        margin-top: 30px;
      }
    }
  }

</style>
