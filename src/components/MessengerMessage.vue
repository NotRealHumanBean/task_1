<template>
        <div class="message">
            <p class="message-text">
                {{ message.message }}
            </p>
            <p :class="checkColor()">{{ likes }}</p>
            <div class="icon-container">
                <a  class="icon-checkmark green" @click="inc()"></a>
                <a  class="icon-cross red" @click="dec()"></a>
            </div>
        </div>
   
</template>

<script>
    export default {
        name: 'MessengerMessage',
        props: {
            message: {
                type: Object,
                default: () => ({}),
            },

        },
        data() {
            return {
                likes: 0
            }
        },
        methods: {
            inc() {
                this.likes++
            },
            dec() {
                this.likes--
            },
            checkColor() {
                let color
                if (this.likes < 0) { color = 'red'}
                else if (this.likes == 0) {color = 'standard'}
                else { color = 'green' }
                return color
            }

        }
    }
</script>

<style lang="css" scoped>
    .message {
        display: flex;
        gap: 30px;
        padding: 20px;
        align-items: center;
        font-size: 24px;
        box-shadow: rgba(9, 30, 66, 0.25) 0px 4px 8px -2px, rgba(9, 30, 66, 0.08) 0px 0px 0px 1px;
    }
    .message p {
        margin: 0;
    }
    .message:hover {
        box-shadow: rgba(9, 30, 66, 0.25) 0px 1px 1px, rgba(9, 30, 66, 0.13) 0px 0px 1px 1px;
        margin-top: 3px;
    }
    .message:not(:last-child){
        margin-bottom: 30px;
    }
    .standard {
        color: #424242;
    }
    .icon-container {
        display: flex;
        flex-direction: column;
    }
    @font-face {
  font-family: 'icomoon';
    src:  url('../assets/fonts/icomoon.eot');
    src:  url('../assets/fonts/icomoon.eot') format('embedded-opentype'),
    url('../assets/fonts/icomoon.ttf') format('truetype'),
    url('../assets/fonts/icomoon.woff') format('woff'),
    url('../assets/fonts/icomoon.svg') format('svg');
  font-weight: normal;
  font-style: normal;
  font-display: block;
}

[class^="icon-"]::before, [class*=" icon-"]::before {
  /* use !important to prevent issues with browser extensions that change fonts */
  font-family: 'icomoon' !important;
  speak: never;
  font-style: normal;
  font-weight: normal;
  font-variant: normal;
  text-transform: none;
  line-height: 1;

  /* Better Font Rendering =========== */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.icon-cross:before {
  content: "\e900";
  width: 30px;
  height: 30px;
}
.icon-checkmark:before {
  content: "\e901";
  font-size: 26px;
}
.green {
    color: rgb(22, 199, 22);
}
.red {
    color: rgb(228, 7, 7);
}
</style>