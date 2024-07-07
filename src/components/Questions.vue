<template>
    <div class="questions-ctr">
        <div class="progress">
            <div class="bar"></div>
            <div class="status" v-if="questionsAnswered">{{questionsAnswered}} out of {{ questions.length }} questions answered</div>
        </div>
        <div class="single-question" 
             v-for="(question,qi) in questions" 
             :key="question.q"
             v-show="questionsAnswered === qi">
            <div class="question">{{question.q}}</div>
            <div class="answers" v-for="answer in question.answers" 
                 :key="answer.text"
                 @click="updateQuestionsAnswered">
                <div class="answer">{{answer.text}}</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['questions', 'questionsAnswered'],
    methods: {
        updateQuestionsAnswered() {
            this.$emit('answerClicked')
        }
    }
}
</script>

<style scoped></style>