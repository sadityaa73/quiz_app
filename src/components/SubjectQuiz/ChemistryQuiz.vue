<template>
  <div id="chem-quiz">
    <countDownTimer/>
  </div>
</template>
<script>
import countDownTimer from "../CountDown/countDownTimer.vue";
export default {
    components:{countDownTimer},
  data() {
    return {};
  },
};
</script>
<style scoped>
#chem-quiz {
  min-width: 70%;
  min-height: 49vh;
  border-radius: 9px;
  box-shadow: 1px 3px 8px 3px grey;
  margin: 1%;
}
</style>
