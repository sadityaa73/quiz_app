<template>
  <div id="main-container">
    <div class="container-two">
      <div class="table-of-question">
        <div class="que-no" v-for="(quiz, id) in quiz" :key="id">
            {{ quiz.id }}
          </div>
      </div>
      <div class="btn-container">
        <button class="final-submit">submit</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  comsponents: {},
  props:['quiz'],
  data() {
    return {};
  },
  created(){
    console.log("printng quiz",this.quiz);
  }
};
</script>
<style scoped>
#main-container {
  min-width: 70%;
  min-height: 88vh;
  border-radius: 9px;
  box-shadow: 1px 3px 8px 3px grey;
  margin: 1%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.container-two {
  border: 1px solid;
  margin: 7px;
  margin-top: 10px;
  width: 85%;
  min-height: 440px;
  border-radius: 6px;
  background: white;
}
.table-of-question {
  margin: 5px;
  min-height: 46vh;
  max-height: 450px;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
.que-no {
  border: 1px solid;
  min-width: 43px;
  min-height: 30px;
  max-height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 7px;
  margin: 10px;
}
.btn-container {
  margin: 7px;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 6vh;
}
.final-submit {
  height: 31px;
  width: 94px;
  border-radius: 5px;
  border: none;
  box-shadow: 0px 0px 4px 1px grey;
  font-size: 19px;
  font-family: cursive;
}
</style>
