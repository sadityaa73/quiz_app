<template>
  <div id="phy-quiz">
    <countDownTimer :subjectName="subjectName" v-if="countDownTimer" />
    <QuestionComponent
      :quiz="phyQuiz"
      :subjectName="subjectName"
      @finalSubmit="submit"
      v-if="questionComponent"
    />
    <submitComponent :quiz="phyQuiz" v-if="isFinalSubmit" />
  </div>
</template>
<script>
import countDownTimer from "../CountDown/countDownTimer.vue";
import QuestionComponent from "../question/QuestionComponent.vue";
import submitComponent from "../submit/submitComponent.vue";
export default {
  components: { countDownTimer, QuestionComponent, submitComponent },
  props: ["subjectName", "phyQuiz"],
  data() {
    return {
      hours: 3,
      minutes: 0,
      seconds: 0,
      isFinalSubmit: false,
      questionComponent: true,
      countDownTimer: true,
    };
  },
  created() {
    this.startCountdown();
  },
  methods: {
    startCountdown() {
      const countdownInterval = setInterval(() => {
        if (this.seconds > 0) {
          this.seconds--;
        } else if (this.minutes > 0) {
          this.minutes--;
          this.seconds = 59;
        } else if (this.hours > 0) {
          this.hours--;
          this.minutes = 59;
          this.seconds = 59;
        } else {
          clearInterval(countdownInterval);
          alert("Countdown is complete!");
        }
      }, 1000);
    },
    submit(event) {
      this.questionComponent = false;
      this.countDownTimer = false;
      this.isFinalSubmit = event;
    },
  },
};
</script>
<style scoped>
#phy-quiz {
  min-width: 90%;
  min-height: 49vh;
  border-radius: 9px;
  box-shadow: 1px 3px 8px 3px grey;
  margin: 1%;
}
</style>
