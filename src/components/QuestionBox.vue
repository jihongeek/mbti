<script>
    export default {     
        props : ['size','index','text']
    }
</script>

<template>
    <div id = "indicator_wrapper">
        <p id = "indicator"> {{index+1}} / {{size}}</p>
    </div>
    <div id = "question_wrapper">
        <p id = "question"> {{ text }}</p>
    </div>
</template>

<style scoped>
    #indicator_wrapper {
        height : 20%;
        margin : 0;
    }
    #indicator {
        font-weight : bold;
        color : rgb(255,255,255);
        font-size : 18px;
    }
    #question_wrapper {
        height : 30%;
        width : 80%;
    }
    #question {
        color : rgb(255,255,255);
        font-size : 24px;
        text-align : center;       
    }
</style>