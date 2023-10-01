<template>
  <div id="main">
    <NavigationBar />
    <HomeSection
      v-if="
        !isPhysicsQuiz && !isChemistryQuiz && !isComputerScienceQuiz && !isStart
      "
      @subjectName="getSubjectName"
    />
    <GeneralNote v-if="isStart" :subjectName="subject" @subject="startQuiz" />
    <PhysicsQuiz
      v-if="isPhysicsQuiz"
      :subjectName="subject"
      :phyQuiz="physicsQuiz"
    />
    <ChemistryQuiz v-if="isChemistryQuiz" :subjectName="subject" />
    <ComputerScienceQuiz v-if="isComputerScienceQuiz" :subjectName="subject" />
  </div>
</template>
<script>
import HomeSection from "../HomeSection/HomeSection.vue";
import NavigationBar from "../Navigation/NavigationBar.vue";
import GeneralNote from "../GeneralNote/GeneralNote.vue";
import PhysicsQuiz from "../SubjectQuiz/PhysicsQuiz.vue";
import ChemistryQuiz from "../SubjectQuiz/ChemistryQuiz.vue";
import ComputerScienceQuiz from "../SubjectQuiz/ComputerScience.vue";
export default {
  components: {
    NavigationBar,
    HomeSection,
    GeneralNote,
    PhysicsQuiz,
    ChemistryQuiz,
    ComputerScienceQuiz,
  },
  data() {
    return {
      isStart: false,
      isPhysicsQuiz: false,
      isChemistryQuiz: false,
      isComputerScienceQuiz: false,
      subject: "",
      physicsQuiz: [
        {
          id: 1,
          question:
            "The instrument that measures and records the relative humidity of air is:",
          Answer: "Hygrometer",
          option: ["Hydrometer", "Hygrometer", "Lactometer", "Barometer"],
        },
        {
          id: 2,
          question: "The shape of our milky way galaxy is:",
          Answer: "spiral",
          option: ["circular", "elliptical", "spiral", "None of the above"],
        },
        {
          id: 3,
          question:
            "The different colours of different stars are due to the variation of:",
          Answer: "temperature",
          option: ["temperature", "pressure", "density", "radiation from them"],
        },
        {
          id: 4,
          question:
            "The fundamental scientific principle in the operation of a battery is:",
          Answer: "dissociation of electrolytes",
          option: [
            "acid-base interaction",
            "dialysis",
            "dissociation of electrolytes",
            "oxidation-reduction",
          ],
        },
        {
          id: 5,
          question:
            "Instrument used to measure the force and velocity of the wind is:",
          Answer: "Anemometer",
          option: ["Ammeter", "Anemometer", "Altimeter", "Audiometer"],
        },
        {
          id: 6,
          question:
            "Which combination of colours is the most convenient during day and night time?",
          Answer: "White and black",
          option: [
            "Organe and blue",
            "White and black",
            "Yellow and blue",
            "Red and green",
          ],
        },
        {
          id: 7,
          question: "Woolen clothes keep the body warm because:",
          Answer: "Wool is a bad conductor",
          option: [
            "Wool increases the temperature of the body",
            "Wool is a bad conductor",
            "Wool absorbs radiant heat from outer objects",
            "Wool rejects heat from the outer objects",
          ],
        },
        {
          id: 8,
          question:
            "If the length of a simple pendulum is halved then its period of oscillation is:",
          Answer: "decreased by a factor",
          option: [
            "doubled",
            "halved",
            "increased by a factor",
            "decreased by a factor",
          ],
        },
        {
          id: 9,
          question: "Equilibrium is a condition that can:",
          Answer: "change only if some internal factor changes.",
          option: [
            "never change.",
            "change only if some external factor changes.",
            "change only if some internal factor changes.",
            "change only if government policies change.",
          ],
        },
        {
          id: 10,
          question:
            "While catching a ball, a player pulls down his hands to lower the:",
          Answer: "momentum",
          option: ["force", "momentum", "impulse", "catching time"],
        },
      ],
      ChemistryQuiz: [
        {
          id: 1,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 2,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 3,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 4,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 5,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 6,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 7,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 8,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 9,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 10,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
      ],
      computerScience: [
        {
          id: 1,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 2,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 3,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 4,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 5,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 6,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 7,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 8,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 9,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
        {
          id: 10,
          question: "",
          Answer: "",
          option: [
            { id: 1, A: "" },
            { id: 2, B: "" },
            { id: 3, C: "" },
            { id: 4, D: "" },
          ],
        },
      ],
    };
  },
  methods: {
    getSubjectName(event) {
      this.subject = event;
      this.isStart = event;
    },
    startQuiz(event) {
      if (event === "physics") {
        this.isStart = false;
        this.isPhysicsQuiz = true;
      } else if (event === "chemistry") {
        this.isStart = false;
        this.isChemistryQuiz = true;
      } else {
        this.isStart = false;
        this.isComputerScienceQuiz = true;
      }
    },
  },
};
</script>
<style scoped>
#main {
  display: flex;
  justify-content: flex-start;
  align-items: flex-start;
  width: 100%;
  border: 1px solid green;
  border-radius: 7px;
  background: #f1f5f4;
}
</style>
