<template>
  <footer class="footer">
    <div class="container footer__container">
      <div class="footer__info">
        <p class="footer__title">
          Адрес
        </p>
        <p class="footer__subtitle">
          г. Ялта, ул. Киевская 60
          <br> офис №4
        </p>
      </div>
      <div class="footer__info">
        <p class="footer__title">
          Телефон
        </p>
        <p class="footer__subtitle">
          +7 978 091 99 98
        </p>
      </div>
      <div class="footer__info">
        <p class="footer__title">
          E-mail
        </p>
        <p class="footer__subtitle">
          info@jalousiegrif.ru
        </p>
      </div>
    </div>
  </footer>
</template>

<style lang="scss">
  .footer {
    background-color: #3d4d3c;
    padding: 60px 15px;
    &__container {
      display: flex;
      justify-content: space-between;
    }
    &__info {
      width: 300px;
      text-align: center;
    }
    &__title {
      font-size: 20px;
      font-weight: bold;
      color: #fff;
      margin-bottom: 25px;
    }
    &__subtitle {
      font-size: 18px;
      color: #9c9c9c;
      line-height: 30px;
    }
  }

  @media(max-width:701px) {
    .footer {
      &__container {
        display: flex;
        flex-direction: column;
        align-items: center;
      }
      &__info {
        &+& {

          margin-top: 30px;
        }
      }
    }
  }

</style>
