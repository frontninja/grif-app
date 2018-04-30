<template>
    <div class="screen">
    <div class=" container screen__container">
      <div class="screen__content">
        <h1 class="screen__title">Салон жалюзи «Гриф»</h1>
        <p class="screen__subtitle">Продажа Жалюзи, Рулонных штор, Роллетных систем, Окна и Двери</p>
        <div class="screen__buttons">
          <button class="button">Получить консультацию</button>
          <button class="button">Вызов замерщика</button>
        </div>
        <p class="screen__alert">
          <i class="icon-exclamation screen__icon" aria-hidden="true"></i> Консультация и вызов мастера на замер БЕСПЛАТНО</p>
      </div>
      <a href="#" class="mouse">
        <div class="mouse__icon"></div>
        <div class="mouse__line"></div>
      </a>
    </div>

  </div>
</template>

<style lang="scss" scoped>
.screen{
    background: url('../assets/images/screen.jpg') center center no-repeat;
    height: 610px;
    background-size: cover;
    color:#fff;
    position: relative;
    &__container{
        display: flex;
        align-items: center;
        height: 100%;
    }
    &__content{
        padding-bottom: 150px;
        margin-left: 120px;
    }
    &__title{
        font-size:48px;
        font-weight: 500;
        letter-spacing: 0.50px;
        margin-bottom: 5px;
    }
    &__subtitle{
        font-size: 18px;
        margin-bottom: 30px;
    }
    &__buttons{
        display: flex;
        margin-bottom: 15px;
    }
    &__alert{
        color:#d2d2d2;
        display: flex;
        align-items: center;
    }
    &__icon{
        color:#00ad5d;
        font-size: 20px;
        margin-right: 5px;
    }
}
@keyframes linemove {
 from { background-position-y: 0; }
 to { background-position-y: 58px; }
}
.mouse{
    display: flex;
    flex-direction: column;
    align-items: center;
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translate(-50%,0);
    &__icon{
        width: 32px;
        height: 49px;
        background: url('../assets/images/mouse.png');
        margin-bottom: 5px
    }
    &__line{
        width: 1px;
        height: 57px;
        background: url('../assets/images/mouse-line.png');
        background-position-y: 0;
        animation: linemove 3s linear infinite;
    }
}

@media(max-width:1200px){
    .screen{
        &__container{
            justify-content: center;
        }
        &__content{
            padding: 0;
            margin: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }
    }
}

@media(max-width:595px){
    .screen{
        &__title{
            font-size: 36px;
        }
        &__subtitle{
            font-size: 16px;
        }
        &__buttons{
            flex-direction: column;
        }
    }
    .button{
        &+&{
            margin-top: 5px;
            margin-left: 0;
        }
    }
}
</style>
