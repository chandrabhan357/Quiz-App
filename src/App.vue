<template>
  <div class="ctr"> 
    <Questions v-if="questionsAnswered < questions.length"
               :questions="questions"
               :questionsAnswered="questionsAnswered"
               @answer-clicked="answerClicked"
    />
    <Result v-else :results="results" :totalCorrect="totalCorrect" />
    <button type="button" class="reset-btn">Reset</button>
  </div>
</template>

<script>
import Questions from './components/Questions.vue';
import Result from './components/Result.vue';

export default {
  name: 'App',
  components: {
    Questions,
    Result
  },
  data() {
    return {
      questionsAnswered: 0,
      totalCorrect: 0,
      questions: [
      {
            id: 0,
            q: 'What temperature does water boil at?', 
            answers: [
                {
                    text: '50 degrees Celcius',
                    is_correct: false
                },
                {
                    text: '25 degrees Celcius',
                    is_correct: false 
                },
                {
                    text: '100 degrees Celcius',
                    is_correct: true
                },
                {
                    text: '150 degrees Celcius',
                    is_correct: false 
                }
            ] 
        },
        {
            id: 1,
            q: 'Who painted the Mona Lisa?', 
            answers: [
                {
                    text: 'Pablo Picasso',
                    is_correct: false
                },
                {
                    text: 'Vincent van Gogh',
                    is_correct: false 
                },
                {
                    text: 'Leonardo Da Vinci',
                    is_correct: true
                },
                {
                    text: 'Claude Monet',
                    is_correct: false 
                }
            ] 
        },
        { 
            id: 2,
            q: 'How many letters are in the word "Banana"?', 
            answers: [
                {
                    text: '5',
                    is_correct: false
                },
                {
                    text: '7',
                    is_correct: false 
                },
                {
                    text: '6',
                    is_correct: true 
                },
                {
                    text: '12',
                    is_correct: false 
                }
            ] 
        },
        { 
            id: 3,
            q: 'Find the missing letter: C_ke', 
            answers: [
                {
                    text: 'e',
                    is_correct: false
                },
                {
                    text: 'a',
                    is_correct: true 
                },
                {
                    text: 'i',
                    is_correct: false 
                },
                {
                    text: 'l',
                    is_correct: false 
                }
            ] 
        },
        { 
            id: 4,
            q: 'How many squares are there on a chess board?', 
            answers: [
                {
                    text: '128',
                    is_correct: false
                },
                {
                    text: '64',
                    is_correct: true 
                },
                {
                    text: '32',
                    is_correct: false 
                },
                {
                    text: '128',
                    is_correct: false 
                }
            ] 
        },
        { 
            id: 5,
            q: 'What does the roman numeral C represent?', 
            answers: [
                {
                    text: '10',
                    is_correct: false
                },
                {
                    text: '100',
                    is_correct: true 
                },
                {
                    text: '1000',
                    is_correct: false 
                },
                {
                    text: '1,000,000',
                    is_correct: false 
                }
            ] 
        },
    ],
    results: [
        {
            min: 0,
            max: 5,
            title: "Try again!",
            desc: "Do a little more studying and you may succeed!"
        },
        {
            min: 6,
            max: 6,
            title: "Wow, you're a genius!",
            desc: "Studying has definitely paid off for you!"
        }
    ]
    }
  },
  methods: {
    answerClicked(is_correct) {
        if(is_correct) {
            this.totalCorrect++;
        }
        this.questionsAnswered+= 1
    }
  },
}
</script>

  

<style scoped>

</style>
