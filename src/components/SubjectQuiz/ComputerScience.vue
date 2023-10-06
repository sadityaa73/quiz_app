<template>
  <div id="comp-quiz">
    <countDownTimer :subjectName ="subjectName"/>
    <QuestionComponent :quiz ="computerQuiz" :subjectName ="subjectName"/>
  </div>
</template>
<script>
import countDownTimer from "../CountDown/countDownTimer.vue";
import QuestionComponent from "../question/QuestionComponent.vue";
export default {
    components:{
        countDownTimer,QuestionComponent,
    },
    props:['subjectName','computerQuiz'],
  data() {
    return {};
  },
};
</script>
<style scoped>
#comp-quiz {
  min-width: 90%;
  min-height: 49vh;
  border-radius: 9px;
  box-shadow: 1px 3px 8px 3px grey;
  margin: 1%;
}
</style>
