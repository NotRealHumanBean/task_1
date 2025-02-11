<template>
  <messenger-body/>
</template>

<script>
import MessengerBody from './components/MessengerBody.vue'

export default {
  name: 'App',
  components: {
    MessengerBody
  }
}
</script>

<style lang="css">
  body {
    background:  #757F9A;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to right, #D7DDE8, #757F9A);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to right, #D7DDE8, #757F9A); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    font-family: "Averia Libre", serif;
  }
  .btn {
    font-family: "Averia Libre", serif;
    font-size: 18px;
    font-weight: 700;
  }

</style>
