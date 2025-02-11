<template>
    <div class="input-container">
        <input type="text" v-model.trim="message">
        <button @click="onSend" class="btn">Send</button>
    </div>
</template>

<script>
    export default {
        name: 'MessengerInput',
        data() {
            return {
                message: null
            }
        },
        methods: {
            onSend() {
                this.$emit('send', this.message)
                this.onClear()
            },
            onClear() {
                this.message = null
            }
        }
    }
</script>

<style lang="css" scoped>
    .input-container {
       display: flex;
       gap: 10px;
       margin-bottom: 80px;
        
    }
    .input-container input {
        padding: 10px;
        height: 40px;
        width: 300px;
        font-family: "Averia Libre", serif;
    }
    .btn {
        color: white;
        transition: all 0.6s ease 0s;
    }
    .btn:hover {
        color: rgb(0, 0, 0);
        border: 1px solid black;
    }

</style>