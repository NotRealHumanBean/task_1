<template>
  <div class="messenger-container">
    <messenger-input @send ="incomingMessage"/>
    <messenger-message  v-for="m in messageArray" :key="m.id"     
    :message="m"/>
  </div>
 

</template>

<script>
import MessengerInput from './MessengerInput.vue'
import MessengerMessage from './MessengerMessage.vue'
export default {
  name: 'MessengerBody',
  components: {
    MessengerInput,
    MessengerMessage
  },
  data() {
    return {
      messageArray: [],

    }
  },
  methods: {
    incomingMessage(sendedMessage) {
      this.messageArray.push(
        {
          id: new Date().getTime(),
          message: sendedMessage,
        }
      )
      console.log(this.messageArray)
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .messenger-container {
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin-top: 60px;
      margin-bottom: 60px;
}

</style>
