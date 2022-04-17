<template>
  <div class="container">
    <h2>Страница с финансовым калькулятором</h2>
    <div class="inputBlocks">
      <div class="inputBLock">
        <h5>Доходы</h5>
        <label>
          Зарплата
          <input type="number" v-model="salary" class="input" />
        </label>
        <label>
          Фриланс
          <input type="number" v-model="freelance" class="input" />
        </label>
        <label>
          Доп. источники
          <input type="number" v-model="dopFinance" class="input" />
        </label>
      </div>
      <div class="inputBLock">
        <h5>Расходы</h5>
        <label>
          Обязательные платежи
          <input type="number" v-model="payments" class="input" />
        </label>
        <label>
          Продукты
          <input type="number" v-model="products" class="input" />
        </label>
        <label>
          Доп. траты
          <input type="number" v-model="dopPayments" class="input" />
        </label>
      </div>
      <div class="inputBLockTotal">
        <div class="total">
          <h5>Доступно в месяц</h5>
          <input class="total-input" type="number" disabled value="totalMonthCalc" v-model="totalMonth"/>
          <span class="hidden">{{totalMonthCalc}}</span>
        </div>
        <div class="total">
          <h5>Доступно в день</h5>
          <input class="total-input" type="number" disabled value="totalDayCalc" v-model="totalDay" />
          <span class="hidden">{{totalDayCalc}}</span>
        </div>
        <div class="total">
          <h5>Накоплю за год</h5>
          <input class="total-input" type="number" disabled value="kopilkaCalc" v-model="kopilka" />
          <span class="hidden">{{kopilkaCalc}}</span>

        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  data() {
    return {
      salary: '' as any,
      freelance: '' as any,
      dopFinance: '' as any,
      payments: '' as any,
      products: '' as any,
      dopPayments: '' as any,
      totalMonth: 0,
      totalDay: 0,
      kopilka: 0,
    };
  },
  computed: {
    totalMonthCalc(): any {
      const salary = Number(this.salary) + Number(this.freelance) + Number(this.dopFinance)
      const payment = Number(this.payments) + Number(this.products) + Number(this.dopPayments)
      if (salary || payment) {
        return this.totalMonth = salary - payment
      }
      return this.totalMonth = 0
    },
    totalDayCalc(): any {
      const day = Math.round(this.totalMonth / 30)
        return this.totalDay = day
    },
    kopilkaCalc(): any {
      const year = Math.round(this.totalMonth * 12)
        return this.kopilka = year
    }
  },
});
</script>

<style scoped>
.input {
  width: 100%;
}
input[type=number]::-webkit-inner-spin-button,
input[type=number]::-webkit-outer-spin-button {
-webkit-appearance: none; margin:0;}
.hidden {
  display: none;
}
.total-input {
  background: #ffffff;
  width: 100%;
}
.total {
  max-width: 250px;
}
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
  max-width: 200px;

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
