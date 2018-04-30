<template>
  <div class="modal-wrapper">
    <div class="modal__overlay">
    </div>

    <div class="modal__box">
      <span class="modal__close icon-close"></span>
      <div class="modal__topline">
        <p class="modal__title">Форма обратной связи</p>
        <p class="modal__subtitle">Оставьте ваши контактные данные и мы вам перезвоним в течении рабочего времени.</p>
      </div>
      <div class="modal__content">
        <form>
          <div class="input__wrapper">
            <!-- <label for="user-name" class="input__label">Имя</label> -->
            <input id="user-name" type="text" class="input" placeholder="Имя">
          </div>
          <div class="input__wrapper">
            <!-- <label for="user-email" class="input__label">Телефон</label> -->
            <input id="user-email" type="email" class="input" placeholder="Номер телефона">
          </div>
          <div class="input__wrapper">
            <!-- <label for="user-email" class="input__label">Коментарий</label> -->
            <textarea id="user-email" class="input input_textfield" placeholder="Комментарий"></textarea>
          </div>
          <div class="modal__actions">
            <button type="submit" class="button">Отправить</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  
}
</script>


<style lang="scss" scoped>
  .modal {
    &__overlay {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: #1313137d;
      z-index: 100;
    }
    &__box {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      background: #fff;
      max-width: 450px;
      padding: 30px;
      position: absolute;
      box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 3px 6px rgba(0, 0, 0, 0.23);
      z-index: 101;
      transform: translate(-50%, -50%);
      top: 50%;
      left: 50%;
    }
    &__close {
      position: absolute;
      font-weight: bold;
      font-size: 25px;
      top: 10px;
      right: 10px;
      cursor: pointer;
    }
    &__topline {
      border-bottom: 1px solid #00ad5d;
      padding-bottom: 15px;
      margin-bottom: 15px;
    }
    &__content {
      width: 100%;
      padding: 0 30px;
    }
    &__actions {
      margin-top: 15px;
    }
    &__title {
      font-size: 24px;
      font-weight: bold;
    }
    &__subtitle {
      font-size: 14px;
      color: #444;
    }
  }

  .input {
    height: 45px;
    line-height: 45px;
    border: none;
    border-bottom: 2px solid #444;
    padding: 0 10px;
    transition: border .3s ease-in-out;
    width: 100%;
    background: #f1f1f1; // width: 200px
    &_textfield {
      height: 90px;
      line-height: 20px;
      width: 100%;
    }
    &:focus {
      outline: none;
      border-bottom: 2px solid #00ad5d;
    }
    &__wrapper {
      display: flex;
      margin-bottom: 15px;
      align-items: center;
      justify-content: flex-end;
    }
    &__label {
      font-size: 18px;
      margin-bottom: 5px;
      margin-right: 15px;
    }
  }

</style>
