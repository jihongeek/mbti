<script>
    import QuestionPage from "./QuestionPage.vue"
    import MainPage from "./MainPage.vue"
    import ResultPage from "./ResultPage.vue"
    const routes = {
        'question' : QuestionPage,
        '': MainPage,
        'result' :ResultPage
    }
    export default {
        data () {
            return {
                currentPath : window.location.hash
            }
        },
        computed: {
            currentView() {
                return routes[this.currentPath.slice(1)] 
            }
        },
        mounted() {
            window.addEventListener('hashchange', () => {
                this.currentPath = window.location.hash    
            })
        }
    }
</script>

<template>
    <component :is="currentView" />
</template>

<style>
    html {
        height: 100%;
    }

    body {
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-color: rgb(35,35,35); 
    }

</style>
