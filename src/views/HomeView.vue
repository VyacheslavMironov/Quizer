<template>
  <div class="row">
    <div class="col-10 p-3 mx-auto">
      <div class="card p-5">
        <div class="col-12">
          <h3>Форма опроса</h3>
        </div>
        <form>
          
          <div class="mb-3">
            <label class="form-label">Введите ФИО</label>
            <input type="text" class="form-control" v-model="foi">
          </div>
          <div class="mb-3">
            <label class="form-label">Укажите возраст</label>
            <input type="text" class="form-control" v-model="age">
          </div>
          <div v-if="step == 0">
            <div class="mb-3">
              <label class="form-label">Каких животных вы любите?</label>
              <p><input type="radio" class="form-check-input" v-model="zver" name="zver" value="Кошки"> Кошки</p>
              <p><input type="radio" class="form-check-input" v-model="zver" name="zver" value="Собаки"> Собаки</p>
            </div>
          </div>
          <div v-if="step == 1">
            <div v-if="zver == 'Кошки'" class="mb-3">
              <label class="form-label">Какую породу кошек вы любите?</label>
              <p><input type="radio" class="form-check-input" v-model="poroda" name="poroda" value="Мейн-кун"> Мейн-кун</p>
              <p><input type="radio" class="form-check-input" v-model="poroda" name="poroda" value="Русская голубая"> Русская голубая</p>
              <p><input type="radio" class="form-check-input" v-model="poroda" name="poroda" value="Ориентал"> Ориентал</p>
            </div>
            <div v-if="zver == 'Собаки'" class="mb-3">
              <label class="form-label">Какую породу собак вы любите?</label>
              <p><input type="radio" class="form-check-input" v-model="poroda" name="poroda" value="Немецкая овчарка"> Немецкая овчарка</p>
              <p><input type="radio" class="form-check-input" v-model="poroda" name="poroda" value="Бульдог"> Бульдог</p>
            </div>
          </div>
          <div v-if="step == 2">
            <div class="mb-3">
              <label class="form-label">Каким шампунем от блох вы моете своего питомца?</label>
              <p><input type="radio" class="form-check-input" v-model="shampun" name="shampun" value="Muzzi"> Muzzi</p>
              <p><input type="radio" class="form-check-input" v-model="shampun" name="shampun" value="БИМФИТО"> БИМФИТО</p>
              <p><input type="radio" class="form-check-input" v-model="shampun" name="shampun" value="OODr"> OODr</p>
              <p><input type="radio" class="form-check-input" v-model="shampun" name="shampun" value="Ecozavr"> Ecozavr</p>
            </div>
          </div>
          <div v-if="step == 3">
            <div class="mb-3">
              <label class="form-label">Какая кличка у вашего домашнего питомца?</label>
              <input type="text" class="form-control" v-model="name">
            </div>
          </div>
          <div class="mb-3">
            <button type="button" v-on:click="otvet" v-if="step < max_step" class="btn btn-primary w-100">Далее</button>
            <button type="button" v-on:click="otvet" v-else class="btn btn-primary w-100">Отправить</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
  export default{
    data() {
      return {
        step: 0,
        max_step: 3,
        zver: null,
        poroda: null,
        shampun: null,
        name: null,
        fio: null,
        age: null
      }
    },
    methods: {
      otvet: function()
      {
        this.step = this.step + 1
      }
    }
  }
</script>


