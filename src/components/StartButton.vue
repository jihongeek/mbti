<script>
    export default {
        methods : {
            moveToQuestionPage() {
                window.location.href = '#question'
            }
        }
    }
</script>

<template>
    <div class ="button_wrapper">
        <button @click = "moveToQuestionPage">시작하기</button>
    </div>
</template>

<style scoped>
    .button_wrapper {
        height :177px;
    }
    button {
        padding : 20px 52.5px;
        border-radius : 20px;
        border-style : none;
        font-size : 24px;
        font-weight: bold;
        color : rgb(255,255,255);
        background-color:rgb(116,78,170) 
    }
</style>