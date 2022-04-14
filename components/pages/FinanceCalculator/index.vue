<template>
  <div class="container">
    <h2>Страница с финансовым калькулятором</h2>
    <div class="inputBlocks">
      <div class="inputBLock">
        <h5>Доходы</h5>
        <label>
          Зарплата
          <input type="number" id="" class="input" />
        </label>
        <label>
          Фриланс
          <input type="number" id="" class="input" />
        </label>
        <label>
          Доп. источники
          <input type="number" id="" class="input" />
        </label>
      </div>
      <div class="inputBLock">
        <h5>Расходы</h5>
        <label>
          Обязательные платежи
          <input type="number" id="" class="input" />
        </label>
        <label>
          Продукты
          <input type="number" id="" class="input" />
        </label>
        <label>
          Доп. траты
          <input type="number" id="" class="input" />
        </label>
      </div>
      <div class="inputBLockTotal">
        <div class="total">
          <h5>Доступно в месяц</h5>
          <input class="total-input" type="number" value="0" id="total-month" />
        </div>
        <div class="total">
          <h5>Доступно в день</h5>
          <input class="total-input" type="number" value="0" id="total-day" />
        </div>
        <div class="total">
          <h5>Накоплю за год</h5>
          <input class="total-input" type="number" value="0" id="kopilka" />
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({});
</script>

<style scoped>
.container {
  padding: 20px;
  font-size: 32px;
}
.inputBlocks {
  display: flex;
}
.inputBLock {
  padding: 15px;
  margin-right: 20px;
}
.inputBLock input {
  margin: 10px;
  font-size: 28px;
}
.inputBLockTotal input {
  margin: 20px;
}
.inputBLockTotal {
  padding: 15px;
}
label {
  font-size: 16px;
  display: flex;
  flex-direction: column;
  margin-top: 20px;
}
h5 {
  margin: 0;
}
.total-input {
  border: 0;
  outline: 0;
  font-size: 36px;
}
</style>
