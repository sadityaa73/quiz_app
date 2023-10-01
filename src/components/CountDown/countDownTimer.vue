<template>
      <div class="timer-clock">
        <div class="subject-name">{{ subjectName.subject }}</div>
        <div class="clock-container">
          {{ hours + ":" + minutes + ":" + seconds }}
        </div>
      </div>
  </template>
  <script>
  export default {
    components:{},
    props:["subjectName"],
    data() {
      return {
        hours: 3,
        minutes: 0,
        seconds: 0,
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
    },
  };
  </script>
  <style scoped>
  .timer-clock {
    min-height: 94px;
    margin: 7px;
    display: flex;
    justify-content: space-between;
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
  .subject-name {
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
    padding-left: 4px;
    padding-right: 4px;
  }
  </style>
  