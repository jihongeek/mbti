<script>
    import QuestionPage from "./QuestionPage.vue"
    
    const routes = {
        '/question' : QuestionPage
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
        mouted() {
            confirm.log(window.location.hash)
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
