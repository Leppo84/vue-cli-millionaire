<template>
  <div class="wrapper">
    <div class="container">      
      <div class="answer">
        <i class="label-left"></i>
        <p class="label" @click="confirmAns(answers.a1_check)">
          {{"A: " + answers.a1 }}
        </p>
        <i class="label-right"></i>
        <i class="label-line"></i>
        <i class="label-left"></i>
        <p class="label" @click="confirmAns(answers.a2_check)">
          {{"B: " + answers.a2 }}
        </p>
        <i class="label-right"></i>
      </div>
    </div>
    <div class="container">
      <div class="answer">
        <i class="label-left"></i>
        <p class="label" @click="confirmAns(answers.a3_check)">
          {{"C: " + answers.a3 }}
        </p>
        <i class="label-right"></i>
        <i class="label-line"></i>
        <i class="label-left"></i>
        <p class="label" @click="confirmAns(answers.a4_check)">
          {{"D: " +  answers.a4 }}
        </p>
        <i class="label-right"></i>
      </div>
    </div>
    <h1 class="score">
          {{this.price[score]}}
        </h1>
  </div>
</template>

<script>
export default {
  name: 'AnswerHolder',
  data(){
    return{
      score : 0,
      price : [
      "500 €",
      "1.000 €",
      "1.500 €",
      "2.000 €",
      "3.000 €",
      "5.000 €",
      "7.000 €",
      "10.000 €",
      "15.000 €",
      "20.000 €",
      "30.000 €",
      "70.000 €",
      "150.000 €",
      "300.000 €",
      "1.000.000 €",
      "HAI VINTO!"
      ]
    }
  },
  props: {
    answers: Object,
  },
  methods: {
    confirmAns(answer) {
      if (answer == true) {
        console.log("risposta corretta " + answer);
        this.$emit('correct-ans');
        return this.score++
      }
      else {
        console.log("risposta errate " + answer);
        this.$emit('wrong-ans');
        return this.score=0
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .container {
    width: auto;
    display: flex;
    flex-direction: row;
    // flex-wrap: nowrap;
    justify-content: center;
    margin-top: 3vh;
  }
  .wrapper {
    width: 75%;
    margin: auto;
  }
  .answer {
    flex-grow: 1;
    max-width: 80%;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: center;
  }
  .label{
    text-align: center;
    flex-grow: 1;
    min-width: 35%;
    display: inline-block;
    background-color: #6a00ff;
    padding: 8px;
  }
  .label-left {
    display: inline-block;
    font-size: 0px; line-height: 0%; width: 0px;
    border-top: 15px solid #14178b;
    border-right: 30px solid #6a00ff;
    border-bottom: 15px solid #14178b;
  }
  .label-right {
    display: block;
    font-size: 0px; line-height: 0%; width: 0px;
    border-top: 15px solid #14178b;
    border-left: 30px solid #6a00ff;
    border-bottom: 15px solid #14178b;
  }
  .label-line {
    flex-grow: 2;
    display: inline-block;
    width: 10%;
  }


</style>
