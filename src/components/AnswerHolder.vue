<template>
  <div class="wrapper">
    <div class="container">      
      <div class="answer">
        <i class="label-left"></i>
        <p class="label" @click="confirmAns(answers.a1_check,1)" v-bind:class="selectedAns == 1 && checkColor === true ?'choice':''">
          {{"A: " + answers.a1 }}
        </p>
        <i class="label-right"></i>
        <i class="label-line"></i>
        <i class="label-left"></i>
        <p class="label" @click="confirmAns(answers.a2_check,2)" v-bind:class="selectedAns == 2 && checkColor === true ?'choice':''">
          {{"B: " + answers.a2 }}
        </p>
        <i class="label-right"></i>
      </div>
    </div>
    <div class="container">
      <div class="answer">
        <i class="label-left"></i>
        <p class="label" @click="confirmAns(answers.a3_check,3)" v-bind:class="selectedAns == 3 && checkColor === true ?'choice':''">
          {{"C: " + answers.a3 }}
        </p>
        <i class="label-right"></i>
        <i class="label-line"></i>
        <i class="label-left"></i>
        <p class="label" @click="confirmAns(answers.a4_check,4)" v-bind:class="selectedAns == 4 && checkColor === true ?'choice':''">
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
      checkColor : null,
      selectedAns : null,
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
      "HAI VINTO 1 MILIONE DI EURO!",
      "Che peccato, Hai perso!"
      ]
    }
  },
  props: {
    answers: Object,
  },
  methods: {
    confirmAns(check,ansNum) {
      this.selectedAns=ansNum;
      this.checkColor=check;
      console.log("risposta scelta " + this.selectedAns);
      if (check == true) {
        setTimeout(() => {
          console.log("risposta corretta " + check);
        }, 2000);
        setTimeout(() => {
          this.$emit('correct-ans');
          this.selectedAns=null;
          this.checkColor=null;

          this.score++
        }, 3000);
      }
      else {
        setTimeout(() => {
          console.log("risposta errata " + check);
          this.score=16;
        }, 2000);
        setTimeout(() => {
          this.$emit('wrong-ans');
          this.selectedAns=null;
          this.checkColor=null;
          this.score=0
        }, 3000);
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
    position: relative;
    cursor:pointer;
    text-align: center;
    text-decoration: none;
    flex-grow: 1;
    min-width: 35%;
    display: inline-block;
    background-color: #6a00ff;
    padding: 8px;
    transition-duration: 0.4s;
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
  .label.selected {
  background-color: red;
}

.label:hover {
  transition-duration: 0.1s;
  background-color: rgb(140, 127, 255);
  filter:brightness(0,6);
}

.label:after {
  content: "";
  display: block;
  position: absolute;
  border-radius: 4em;
  left: 0;
  top:0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: all 0.5s;
  box-shadow: 0 0 10px 40px white;
}

.label:active:after {
  box-shadow: 0 0 0 0 white;
  position: absolute;
  left: 0;
  top:0;
  opacity: 1;
  transition: 0s;
}

.button:active {
  top: 1px;
}
  .choice {
  animation: clicked 3s;
}
@keyframes clicked {
  0% {
    background-color: #6a00ff;
  }
  66% {
    background-color: #6a00ff;
  }
  75% {
    background-color: green;
  }
  100% {
    background-color: green;
  }
}
// @keyframes clickedWrong {
//   0% {
//     background-color: #6a00ff;
//   }
//   50% {
//     background-color: red;
//   }
//   100% {
//     background-color: #6a00ff;
//   }
// }


</style>
