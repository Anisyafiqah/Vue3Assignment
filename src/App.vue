<template>

<div class="card">
  <div class="card-content">
    <div class="card-title>">
      <h2>Vue3 Assignment</h2>
      <div class="underline-title"></div>

      <input class="input" type="number" v-model="counter" placeholder="Enter starting value" min="0"/>
      <!-- @input="updateCount($event.target.value)" -->
   

  <CounterView :counter="counter" @increment="increment" @decrement="decrement" @multipleOfFive="logCount"/>
  <LoggerView ref="logger" :logs="logs" />

    </div>
  </div>
</div>

</template>

<script>
import CounterView from './components/CounterView.vue';
import LoggerView from './components/LoggerView.vue';

export default {
  components: {
    CounterView,
    LoggerView
  },
  data() {
    return {
      counter: 0,
      logs: []
    };
  },
  methods: {
    logCount(value, doubledValue) {
      this.logs.push({
        id: Date.now(),
        message: `Count value: ${value} | Doubled value: ${doubledValue}`
      });
    },
    // updateCount(counter) {
    //   if (counter === '') {
    //     this.count = 0;
    //   } else {
    //     this.count = parseInt(counter);
    //   }
    // }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  background: -webkit-linear-gradient(bottom, #8d5256, #761c1c);
  min-height: 100vh;
}

.card-title{
  /* font-family: "Raleway Thin", sans-serif; */
  letter-spacing: 4px;
  padding-bottom: 23px;
  padding-top: 13px;
  text-align: center;
}

.card {
  background: #fbfbfb;
  border-radius: 8px;
  box-shadow: 1px 2px 8px rgba(0, 0, 0, 0.65);
  height: 100%;
  margin: 6rem auto 8.1rem auto;
  max-width: 80%;
}

.card-content {
  padding: 12px 44px;
}

.underline-title {
  background: -webkit-linear-gradient(right, #eb91a4, #a73131);
  height: 2px;
  margin: -1.1rem auto 0 auto;
  width: 200px;
}

.input {
  margin-top:50px;
  padding: 2rem 1rem;
  font-size: 2rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
  text-align: center;
}
</style>
