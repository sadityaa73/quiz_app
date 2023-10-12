<template>
  <div id="chem-quiz">
    <countDownTimer :subjectName="subjectName" v-if="countDownTimer" />
    <QuestionComponent
      :quiz="chemQuiz"
      :subjectName="subjectName"
      @finalSubmit="submit"
      v-if="questionComponent"
    />
    <submitComponent :quiz="chemQuiz" v-if="isFinalSubmit" />
  </div>
</template>
<script>
import countDownTimer from "../CountDown/countDownTimer.vue";
import QuestionComponent from "../question/QuestionComponent.vue";
import submitComponent from "../submit/submitComponent.vue";
export default {
  components: { countDownTimer, QuestionComponent,submitComponent },
  emits:['finalSubmit'],
  props: ["subjectName", "chemQuiz"],
  data() {
    return {
      isFinalSubmit: false,
      questionComponent: true,
      countDownTimer: true,
    };
  },
  methods: {
    submit(event) {
      this.questionComponent = false;
      this.countDownTimer = false;
      this.isFinalSubmit = event;
    },
  },
};
</script>
<style scoped>
#chem-quiz {
  min-width: 90%;
  min-height: 49vh;
  border-radius: 9px;
  box-shadow: 1px 3px 8px 3px grey;
  margin: 1%;
}
</style>
