<template>
    <div class="questions-ctr">
        <div class="progress">
            <div class="bar" :style="{ width: `${(questionsAnswered / questions.length)* 100}%` }"></div>
            <div class="status">{{questionsAnswered}} out of {{ questions.length }} questions answered</div>
        </div>
        <div class="single-question" 
             v-for="(question, qi) in questions" 
             :key="question.q">
            <div v-if="questionsAnswered === qi">
                <div class="question">{{question.q}}</div>
                <div class="answers" >
                    <div class="answer" 
                         v-for="answer in question.answers" 
                         :key="answer.text"
                         @click="selectAnswer(answer.is_correct)"> 
                         {{answer.text}}
                    </div>
                </div>
            </div> 
        </div>
    </div>
</template>

<script>
export default {
    props: ['questions', 'questionsAnswered'],
    emits: ["answerClicked"],
    methods: {
        selectAnswer(is_correct) {
            this.$emit('answerClicked', is_correct);
        }
    }
}
</script>

<style scoped></style>