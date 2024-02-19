<template>
  <div class="counter">
    <button @click="increment">
      <span class="material-symbols-outlined">add</span>
    </button>
    
    <!-- <input type="number" v-model="count" placeholder="Enter starting value" min="0"/>
    @input="updateCount($event.target.value)" -->

    <button @click="decrement">
      <span class="material-symbols-outlined">remove</span>
    </button>
  </div>

  <div>
  <table>
    <tr>
        <th><h4>Count Value</h4></th>
        <th><h4>Doubled Count Value</h4></th>
      </tr>
      <tr>
        <td>
          <span>{{ displayCount }}</span>
        </td>
        <td>
          <span>{{ doubledCount }}</span>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    counter: {
      type: Number,
      default: 0,
    }
  },
  data() {
    return {
      count: this.counter,
    };
  },
  computed: {
    doubledCount() {
      return this.count * 2;
    },
    displayCount() {
      return this.count || 0;
    }
  },
  // props: [count],
  // computed: {
  //   doubledCount() {
  //     return this.count * 2;
  //   }
  // },
  methods: {
    increment() {
      this.count++;
    },
    decrement() {
      if (this.count > 0) {
        this.count--;
      }
    },

    // updateCount(value) {
    //   this.count = value;
    //     if (value === '') {
    //     this.count = 0;
    //   } else {
    //     this.count = parseInt(value);
    //   }
    // },

    // updateCount(value) {
    //   this.count = value;
    // },

    // increment() {
    //   this.$emit('increment');
    // },
    // decrement() {
    //   this.$emit('decrement');
    // },
    // updateCount(event) {
    //   this.$emit('update-count', event.target.value);
    // },
    
    // checkMultipleOfFive() {
    //   if (this.count % 5 === 0) {
    //     this.$emit('multipleOfFive', this.count, this.count * 2);
    //   }
    // }
  },
  watch: {
  count(newValue) {
    if (newValue % 5 === 0 && newValue != 0) {
      alert('Warning: Value reached multiple of 5!');
      this.$emit('multipleOfFive', newValue, newValue * 2);
    }
  },
  counter(newCounter) {
    this.count = newCounter;
  }
}
};
</script>

<style>

.counter {
  margin-top: -80px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0rem 15rem;
}

.counter button {
  padding: 0.5rem 1rem;
  font-size: 2rem;
  background-color: #7b191f;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.counter span {
  font-size: 1.5rem;
  font-weight: bold;
}

table {
  margin: 30px auto;
  vertical-align: middle;
}

th {
  padding: 0.5rem 0.5rem;
  text-align: center;
  vertical-align: middle;
}

td {
  text-align: center;
  vertical-align: middle;
  font-size: 2rem;
  font-weight: bold;
  border: 1px solid #7b191f;
  border-radius: 100px;
  padding: 1rem 10rem;
}

td:hover {
  background-color: #7b191f;
  color:white;
}
</style>