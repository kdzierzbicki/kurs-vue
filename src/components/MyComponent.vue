<template>

  <div>

  <h1>Price: {{price}}</h1>
    <button @click="makeOrder">Make next order</button>

    <p>quantity: {{quantity}}</p>
    <p>Order total price: {{totalPrice}}</p>
    <p>Tax: {{tax}}</p>

  </div>

</template>

<script>
import {ref} from 'vue'
export default {
  name: "MyComponent",

  setup() {

    const quantity = ref(0);
    const price = ref(100);
    const totalPrice = ref(0);
    const tax = ref(0);

      function makeOrder(){

        quantity.value++;
        totalPrice.value = quantity.value * price.value;
        tax.value = totalPrice.value * 0.23;
      }
    return{makeOrder, quantity, price, totalPrice, tax,};
  }

  };

</script>
