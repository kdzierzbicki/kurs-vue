<template>

  <div>

    <button @click="SeyHello"> wciśnij aby się przywitać</button>

  </div>

</template>

<script>
export default {
  name: "MyComponent",

  setup() {

      function SeyHello() {

        const welcometext = "siema, jak leci?";

        console.log(addExclamationMark(welcometext));
      }

    function addExclamationMark(text){


        return {text};
    }
        return {SeyHello};
  }

  };

</script>
