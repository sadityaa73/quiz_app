<template>
  <div id="comp-quiz">
    <countDownTimer :subjectName ="subjectName" v-if="countDownTimer"/>
    <QuestionComponent :quiz ="computerQuiz" :subjectName ="subjectName"  @finalSubmit="submit" v-if="questionComponent"/>
    <submitComponent :quiz ="computerQuiz" v-if="isFinalSubmit"/>
  </div>
</template>
<script>
import countDownTimer from "../CountDown/countDownTimer.vue";
import QuestionComponent from "../question/QuestionComponent.vue";
import submitComponent from "../submit/submitComponent.vue";
export default {
    components:{
        countDownTimer,QuestionComponent,submitComponent
    },
    emits:['finalSubmit'],
    props:['subjectName','computerQuiz'],
  data() {
    return {
      isFinalSubmit: false,
      questionComponent: true,
      countDownTimer: true,
    };
  },
  methods:{
    submit(event) {
      this.questionComponent = false;
      this.countDownTimer = false;
      this.isFinalSubmit = event;
    },
  }
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
