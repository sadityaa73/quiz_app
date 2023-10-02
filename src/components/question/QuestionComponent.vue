<template>
  <div class="main-container">
    <div class="container-one">
      <div class="question-container">
        {{ quiz[currentQuestion].question }}
      </div>
      <div class="answer-container">
        <div class="options" @click="selected(`${quiz[currentQuestion].A}`)">
          {{ quiz[currentQuestion].A }}
        </div>
        <div class="options" @click="selected(`${quiz[currentQuestion].B}`)">
          {{ quiz[currentQuestion].B }}
        </div>
        <div class="options" @click="selected(`${quiz[currentQuestion].C}`)">
          {{ quiz[currentQuestion].C }}
        </div>
        <div class="options" @click="selected(`${quiz[currentQuestion].D}`)">
          {{ quiz[currentQuestion].D }}
        </div>
      </div>
      <div class="btn-container">
        <button
          class="previous-btn"
          @click="previousQuestion()"
          v-if="currentQuestion > 0"
        >
          previous & save</button
        ><button class="next-btn" @click="nextQuestion()">next & save</button>
      </div>
    </div>
    <div class="container-two">
      <div class="table-of-question">
        <div class="que-no" v-for="(quiz, id) in quiz" :key="id">
          {{ quiz.id }}
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  components: {},
  props: ["quiz"],
  data() {
    return {
      score: "",
      totalScore: "",
      currentQuestion: 0,
      isPrevious: false,
    };
  },
  created() {
    console.log("printing nested array at created", this.quiz);
  },
  methods: {
    nextQuestion() {
      var attemptedQuestion = document.querySelectorAll(".que-no");
      console.log("print length of que-no", attemptedQuestion.length);

      ("lightGreen");
      for (let i = 0; i < attemptedQuestion.length; i++) {
        if (this.currentQuestion === i) {
          attemptedQuestion[i].style.backgroundColor = "lightGreen";
        }
      }

      if (this.currentQuestion >= this.quiz.length - 1) {
        alert("you attemped all questions");
      } else {
        this.currentQuestion++;
        var selectedOption = document.querySelectorAll(".options");
        selectedOption.forEach((element) => {
          element.style.color = "";
        });
      }
    },
    previousQuestion() {
      if (this.currentQuestion >= 0) {
        this.currentQuestion--;
      }
    },
    selected(select) {
      console.log(select);

      var selectedOption = document.querySelectorAll(".options");

      selectedOption.forEach(function (selection) {
        selection.addEventListener("click", function (event) {
          event.stopPropagation();
          selectedOption.forEach((element) => {
            element.style.color = "";
          });
          this.style.color = "red";
        });
      });
    },
  },
};
</script>
<style scoped>
.main-container {
  margin: 7px;
  display: flex;
}
.container-one {
  border: 1px solid;
  margin: 7px;
  margin-top: 10px;
  width: 60%;
  min-height: 55px;
  border-radius: 6px;
  background: white;
}
.question-container {
  border: 1px solid;
  margin: 6px;
  width: 95%;
  min-height: 55px;
  padding: 7px;
  border-radius: 6px;
  background: white;
}
.answer-container {
  border: 1px solid;
  margin: 7px;
  max-width: 100%;
  min-height: 349px;
  margin-top: 28px;
  border-radius: 6px;
  background: white;
  display: flex;
  justify-content: center;
  flex-direction: column;
}
.options {
  border: 1px solid;
  max-width: fit-content;
  min-height: 30px;
  min-width: 289px;
  padding-left: 7px;
  padding-right: 7px;
  display: flex;
  justify-content: flex-start;
  align-items:center;
  font-size: 19px;
  margin: 10px;
}
.btn-container {
  margin: 7px;
  min-height: 36px;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}
.previous-btn {
  margin-left: 6px;
  margin-right: 63%;
  height: 32px;
  border-radius: 7px;
  border: none;
  background: #2a8ff7;
  color: white;
}
.next-btn {
  margin-right: 6px;
  height: 32px;
  border-radius: 7px;
  border: none;
  background: #2a8ff7;
  color: white;
}
.container-two {
  border: 1px solid;
  margin: 7px;
  margin-top: 10px;
  width: 35%;
  min-height: 55px;
  border-radius: 6px;
  background: white;
}
.table-of-question {
  border: 1px solid;
  margin: 5px;
  max-height: 450px;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
.que-no {
  border: 1px solid;
  min-width: 34px;
  min-height: 30px;
  max-height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 7px;
  margin: 10px;
}
.focused {
  background: "green";
}
</style>
