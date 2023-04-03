<template>
  <main class="wrapper">
    <button :class="randomIndex==null? '' : 'd-none'" id="btn-start" class="" @click="generateRandomIndex">INIZIAMO LA SCALATA AL MILIONE!</button>
    <!-- <h1>{{ quiz[1].question }}</h1> -->
    <QuestionHolder :questions="quiz[randomIndex]"/>
    <AnswerHolder :answers="quiz[randomIndex]"/>
  </main>
</template>

<script>
import QuestionHolder from './QuestionHolder.vue'
import AnswerHolder from './AnswerHolder.vue'

export default {
  components: { QuestionHolder, AnswerHolder },
  name: 'ContainerMain',
  data() {
    return {
      randomIndex : null,
      quiz: [
        {
          question: "Q 0",
          a1: "A 0",
          a1_check: false,
          a2: "B 0",
          a2_check: false,
          a3: "C 0",
          a3_check: false,
          a4: "D 0",
          a4_check: false,
        },
        {
          question: "Q 1",
          a1: "A 1",
          a1_check: false,
          a2: "B 1",
          a2_check: false,
          a3: "C 1",
          a3_check: false,
          a4: "D 1",
          a4_check: false,
        },
        {
          question: "Q 2",
          a1: "A 2",
          a1_check: false,
          a2: "B 2",
          a2_check: false,
          a3: "C 2",
          a3_check: false,
          a4: "D 2",
          a4_check: false,
        },
        {
          question: "Q 3",
          a1: "A 3",
          a1_check: false,
          a2: "B 3",
          a2_check: false,
          a3: "C 3",
          a3_check: false,
          a4: "D 3",
          a4_check: false,
        },
      ],
    }
  },
  methods: {
    generateRandomIndex() {
      this.randomIndex = Math.floor(Math.random() * this.quiz.length);
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .wrapper {
    width: 75%;
    margin: auto;
    text-align: center;
  }
  .d-none{
    display: none;
  }

  #btn-start{
    color: white;
    text-align: center;
    margin: auto;
    margin-bottom: 80px;
    flex-grow: 1;
    min-width: 35%;
    background-color: #6a00ff;
    padding: 8px;
    border-radius: 100rem;
  }

</style>
