<template>
  <div id="main-container">
    <div class="timer-clock">
      <div class="clock-container">
        {{ "03" + ":" + "00" + ":" + "00" }}
      </div>
    </div>
    <div class="advisory-container">
      <div class="no-of-question-marks">
        <div class="no-of-question">Total Questions: 20</div>
        <div class="total-marks">Total Marks: 20</div>
      </div>
      <hr />
      <div class="key-points">
        <ul class="points">
          <li>This section consisit 20 question.</li>
          <li>Total marks is 20,each question having 1 marks .</li>
          <li>Read all question properly before selecting answer for that.</li>
          <li>No negative marks in deducted for any question.</li>
          <li>
            Please give answer for all the question that is given in this
            section.
          </li>
          <li>
            Once you start please make it sure that you can leave after when all
            you answer in submited.
          </li>
        </ul>
      </div>
    </div>
    <div class="btn-container">
      <button class="start-btn">Start</button>
    </div>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {};
  },
};
</script>
<style scoped>
#main-container {
  min-width: 70%;
  min-height: 49vh;
  border-radius: 9px;
  box-shadow: 1px 3px 8px 3px grey;
  margin: 1%;
}
.timer-clock {
  min-height: 94px;
  margin: 7px;
  display: flex;
  justify-content: flex-end;
}
.clock-container {
  border: 1px solid;
  min-width: 156px;
  height: 45px;
  margin: 6px;
  border-radius: 7px;
  background: #2a8ff7;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 25px;
}
.advisory-container {
  margin: 7px;
  min-height: 455px;
  border-radius: 10px;
  background: white;
  box-shadow: 0px 1px 5px -1px grey;
}
.no-of-question-marks {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  margin: 8px;
  min-height: 45px;
  margin-top: 6px;
  margin-bottom: 1px;
}

.no-of-question {
  border-radius: 5px;
  min-width: 100px;
  min-height: 35px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  margin-left: 6px;
  font-size: 16px;
  background: #2a8ff7;
  color: white;
  padding-left: 6px;
  padding-right: 6px;
}

.total-marks {
  border-radius: 5px;
  min-width: 100px;
  min-height: 35px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  margin-left: 6px;
  font-size: 16px;
  background: #2a8ff7;
  color: white;
  padding-left: 6px;
  padding-right: 6px;
}

hr {
  margin: 7px;
  border: 0.5px solid;
  margin-top: 0px;
  margin-bottom: 0px;
}
.key-points {
  border: 1px solid;
  margin: 8px;
  min-height: 380px;
  margin-top: 6px;
  border-radius: 0px 0px 7px 7px;
}

.points {
  margin: 22px;
  list-style: number;
  min-height: 29px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  padding: 0px;
}

li {
  font-size: 18px;
  margin-bottom: 10px;
}
.btn-container {
  margin: 7px;
  min-height: 36px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.start-btn {
  width: 100px;
  height: 32px;
  border-radius: 7px;
  border: none;
  background: #2a8ff7;
  color: white;
  font-size: 18px;
}
</style>
