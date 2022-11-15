<template>

  <div>
  <!-- jeżeli używasz toReds piszemy wtedy zmienne bez state -->
  <h1>Price: {{state.price}}$</h1>
    <button @click="makeOrder">Make next order</button>

    <p>quantity: {{state.quantity}}</p>
    <p>Order total price: {{state.totalPrice}}</p>
    <p>Tax: {{state.tax}}</p>

  </div>

</template>

<script>
import {reactive} from 'vue'
//import {reactive, toRefs} from 'vue'
export default {
  name: "MyComponent",

  setup() {

      const state = reactive({

        quantity: 0,
        price: 100,
        totalPrice: 0,
        tax: 0,
      });

    function makeOrder(){

      state.quantity++;
      state.totalPrice = state.quantity * state.price;
      state.tax= state.totalPrice * 0.23;
    }



    return{makeOrder, state};

      //return{makeOrder, ...toRefs(state)};
  }

  };

</script>
