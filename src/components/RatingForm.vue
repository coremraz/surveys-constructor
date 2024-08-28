<template>
  <h2>Сколько Вам лет?</h2>
  <div class="radio-answers">
    <input class="radio-answer" type="radio" value="10-14" id="age1">
    <label for="age1">10-14</label>

    <input class="radio-answer" type="radio" value="14-18" id="age2">
    <label for="age2">14-18</label>

    <input class="radio-answer" type="radio" value="18-24" id="age3">
    <label for="age3">18-24</label>

    <input class="radio-answer" type="radio" value="24+" id="age4">
    <label for="age4">24+</label>
  </div>
</template>
<script>
export default {
  name: 'RadioForm'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .radio-answers {
    display: flex;
    flex-direction: column;
  }

  /* Скрываем стандартный input */
  input[type="radio"] {
    position: absolute;
    opacity: 0;
  }

  /* Стилизуем label как контейнер для кастомного radio */
  label {
    display: inline-block;
    position: relative;
    padding-left: 25px;
    cursor: pointer;
  }

  /* Создаем кастомный кружок с помощью ::before */
  label::before {
    content: "";
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    width: 16px;
    height: 16px;
    border-radius: 50%;
    border: 2px solid #ccc;
  }

  /* Изменяем стили при наведении */
  label:hover::before {
    border-color: #aaa;
  }

  /* Изменяем стили для выбранного radio */
  input[type="radio"]:checked + label::before {
    background-color: #333;
    border-color: #333;
  }

  /* Добавляем точку внутри выбранного radio */
  input[type="radio"]:checked + label::after {
    content: "";
    display: block;
    position: absolute;
    top: 50%;
    left: 50%;
    width: 8px;
    height: 8px;
    background-color: #fff;
    border-radius: 50%;
    transform: translate(-50%, -50%);
  }

</style>
