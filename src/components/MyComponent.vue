<template>

  <!-- jeżeli używasz toReds piszemy wtedy zmienne bez state. State podajemy do zmiennych przy reactive. Watch używamy to obserowania czegoś w konsoli-->

  <div>
  <p> Masks: {{masks}}</p>
    <p v-if="masks >3">You buy a mask</p>
    <p v-else-if="masks > 0 && masks <= 3">You can buy a mask, but hurry up!</p>
    <p v-else>You can't buy a mask, out of stock</p>
    <button v-if="masks" @click="buyMasks">Buy a mask</button>

  </div>

</template>

<script>
import {ref} from "vue";

export default {
  name: "MyComponent",

  setup() {

      const masks = ref(5);

      function buyMasks(){
      masks.value--;

      }
      return {masks, buyMasks}
        }


  };
</script>
