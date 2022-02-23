<script>
    import AnswerBox from "./components/AnswerBox.vue";
    import QuestionBox from "./components/QuestionBox.vue";
    export default {
        data() {
            return {
                questionIdx: 0,
                score: [0, 0, 0, 0],
                questions: [
                    {
                        text: "잔잔하고 감성적인 음악 VS 신나는 음악?",
                        type: 0,
                        yes: '감성적인 음악',
                        no: '신나는 음악'
                    },
                    {
                        text: "노래 들을 때, 가사 VS 멜로디",
                        type: 0,
                        yes: '가사가 더 중요!',
                        no: '멜로디가 더 중요!'
                    },
                    {
                        text: "공부나 일을 할 때 음악을 들으면서 하는 편인가요?",
                        type: 1,
                        yes: '네',
                        no: '아니요'
                    },
                    {
                        text: "길 가면서 음악을 듣나요?",
                        type: 2,
                        yes: '네',
                        no: '아니요'
                    },
                ],
            }
    },
    components : { 
        'question-box' : QuestionBox,
        'answer-box' : AnswerBox
    },
    methods: {
        returnScore(type) {
            if (this.questionIdx == this.questions.length)
            {
                console.log("끝남")
            }
            else 
            {
                if (this.questionIdx < this.questions.length - 1)
                {
                    this.score[type]++;
                    this.questionIdx++
                }
            }
            
        }
    }            
    }           
</script>

<template>
    <question-box :index = "questionIdx" :size = "questions.length" :text = "questions[questionIdx].text" />
    <answer-box :type = "questions[questionIdx].type" :yes = questions[questionIdx].yes :no = questions[questionIdx].no @return-score = "returnScore"/> 
</template>

<style>
    #app {
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 25px;
    }
</style>