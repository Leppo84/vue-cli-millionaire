<template>
  <div class="wrapper">
    <div class="container">      
      <div class="answer">
        <i class="label-left"></i>
        <p class="label">
          {{ answers.a1 }}
        </p>
        <i class="label-right"></i>
        <i class="label-line"></i>
        <i class="label-left"></i>
        <p class="label">
          {{ answers.a2 }}
        </p>
        <i class="label-right"></i>
      </div>
    </div>
    <div class="container">
      <div class="answer">
        <i class="label-left"></i>
        <p class="label">
          {{ answers.a3 }}
        </p>
        <i class="label-right"></i>
        <i class="label-line"></i>
        <i class="label-left"></i>
        <p class="label">
          {{ answers.a4 }}
        </p>
        <i class="label-right"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AnswerHolder',
  props: {
    answers: Array,
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
