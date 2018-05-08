<template>
    <section class="section">
      <div class="container">
          <h1 class="title1">Контакты</h1>
          <div class="flex-wrap">
            <div class="flex-column">
              <div class="contacts-block">
                <div class="contacts-block__item">
                  <i class="icon-location-pin contacts-block__icon"></i>
                  <div>
                    <p class="contacts-block__title">Адрес</p>
                    <p class="contacts-block__subtitle">г. Ялта, ул. Киевская 60, Офис №4</p>
                  </div>
                </div>
                <div class="contacts-block__item">
                  <i class="icon-phone contacts-block__icon"></i>
                  <div>
                    <p class="contacts-block__title">Телефон</p>
                    <p class="contacts-block__subtitle">+7 978 091 99 98</p>
                  </div>
                </div>
                <div class="contacts-block__item">
                  <i class="icon-envelope contacts-block__icon"></i>
                  <div>
                    <p class="contacts-block__title">E-mail</p>
                    <p class="contacts-block__subtitle">info@salongrif.ru</p>
                  </div>
                </div>
              </div>
            </div>
            <div class="flex-column">
              <form class="form">
                <div class="input__box">
                <input type="text" name="Имя" placeholder="Имя" class="input">
                <input type="email" name="E-mail" placeholder="E-mail" class="input">
                </div>
                <div class="input__box">
                <input type="text" name="Тема" placeholder="Тема сообщения" class="input">
                </div>
                <div class="input__box">
                <textarea name="сообщение" rows="5" placeholder="Текст сообщения" class="textarea"></textarea>
                </div>
                <button class="button">Отправить</button>
              </form>
            </div>
          </div>
      </div>
    </section>
</template>
<script>
  
</script>

<style lang="scss" scoped>
  
  .flex-wrap{
    display: flex;
    margin: 0 -15px;
  }

  .flex-column{
    width: 50%;
    padding: 15px;
  }

  .contacts-block{
    &__item{
      display: flex;
      align-items: center;
      &+&{
        margin-top: 60px;
      }
    }
    &__icon{
      font-size: 45px;
      color:#00ad5d;
      margin-right: 50px;
    }
    &__title{
      font-size: 20px;
      font-weight: bold;
      color:#3c4d3c;
      margin-bottom: 15px;
    }
    &__subtitle{
      font-size: 18px;
      color:#809c83;
    }
  }
</style>

