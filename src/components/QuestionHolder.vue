<template>
  <div class="label">
    <!-- <div v-for="(question, index) in questions" :key="index" class="label"> -->
      <h1 class="diamond">
        <!-- placeholder  -->
        {{questions.question}}
      </h1>
    <!-- </div> -->
  </div>
</template>

<script>
export default {
  name: 'QuestionHolder',
  props: {
    questions: Array,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

body *{
  width: 100%;
  position: relative;
  display: block;
  margin: 0 auto;
  padding: 0;
  text-align: center;
  z-index: 100;
}
a{
  color: inherit;
  text-decoration: none;
  outline: 0;
}
.label{
  width: 60%;
  padding: 1%;
}

h1{
  font-size: 1rem;
  line-height: 50px;
  margin: auto;
  z-index: auto;
  cursor: default; 
}
h1:before, 
h1:after {
  content: '';
  position: absolute;
  height: 0;
  width: 0;
  border-style: solid;
  border-width: 0;
}
.diamond {
  background-color: #6a00ff; 
  text-align: center;
}
.diamond:after, 
.diamond:before {
  border-color: transparent #6a00ff;
}
.diamond:before {
  left: -25px;
  border-width: 25px 25px 25px 0;
}
.diamond:after {
  right: -25px;
  border-width: 25px 0 25px 25px;
}
</style>
