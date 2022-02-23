<script>
    export default {
        props : ['type', 'yes', 'no'],
        emits : ['returnScore']
    }
</script>

<template>
    <div>
        <button id = "yes_button" @click = "$emit('returnScore',this.type)"> {{yes}} </button>
    </div>
    <div>
        <button id = "no_button" @click = "$emit('returnScore',this.type)"> {{no}} </button>
    </div>
</template>

<style scoped>
    button {
        padding : 16px 72px;
        border-radius : 20px;
        border-style : none;
        font-size : 18px;
    }
    #yes_button {
        background-color : rgb(226,216,123);
        color : rgb(255,255,255);
    }
    #no_button {
        background-color : rgb(123,183,226);
        color : rgb(255,255,255);
    }
</style>