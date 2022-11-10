
<template>
   <div class="container">
      <img alt="logo" class="img" src="./assets/spiral.png">   
      <h1> Fibonacci calculator </h1>
      <div class="inputWrapper">
         <input class="inputPlace" type="number" placeholder="Input" v-model="number">
         <label class="inputPlace">{{ fibonacci }} </label>
      </div>
      <button v-on:click="fibonacciSequence">Calculate</button>
   </div>
</template>

<script>
export default {
  data() {
    return {
      number: null,
      fibonacci: "Result: XX"
    }
  },
  methods: {
    fibonacciSequence: function() {
     let fib = [];
     let result = [];

      fib[0] = 0;
      fib[1] = 1;
      for (let i = 2; i < this.number; i++) {
        // Next fibonacci number = previous + one before previous
        fib[i] = fib[i - 2] + fib[i - 1];
        result.push(fib[i]);
      }
      result.unshift(1);
      result.unshift(0);
      
      this.fibonacci = result;
      
    }
  }
}
</script>

