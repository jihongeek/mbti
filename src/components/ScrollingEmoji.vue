<script>
    import { markRaw } from "vue";
    import Guitar from "./emojis/Guitar.vue"
    import Drum from "./emojis/Drum.vue";
    import Microphone from "./emojis/Microphone.vue";
    import Saxophone from "./emojis/Saxophone.vue";
    
    export default {
        data() {
            return {
                emojis : [Guitar,Drum,Microphone,Saxophone,Guitar].map(x => markRaw(x))
            }
        },
        mounted() {
            const container = document.getElementsByClassName("container")[0]
            container.addEventListener("animationiteration", () => {
                this.emojis.pop()
                this.emojis.unshift(this.emojis[this.emojis.length-1])
            })
        }
    }
</script>

<template>
    <div class = "emoji_wrapper">
        <div class = "container">
            <component v-for = "emoji in emojis" :is = emoji></component>
        </div>
    </div>
</template>

<style>
    .emoji_wrapper {
        overflow: hidden;
        height: 123px;
        width : 311px;
    }
    @keyframes emoji {
        0%   {left: -50px; top:0px;}
        100%  {left: 37px; top:0px;}
    }
    .container {
        display: flex;
        height : 50px;
        width : 398px;
        gap : 37px;
        position: relative;
        animation-name: emoji;
        animation-duration: 3.5s;
        animation-timing-function: linear;
        animation-iteration-count: infinite;
        animation-direction: normal;
    }
</style>