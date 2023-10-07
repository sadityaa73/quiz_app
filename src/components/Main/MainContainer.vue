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
    <ChemistryQuiz
      v-if="isChemistryQuiz"
      :subjectName="subject"
      :chemQuiz="ChemistryQuiz"
    />
    <ComputerScienceQuiz
      v-if="isComputerScienceQuiz"
      :subjectName="subject"
      :computerQuiz="computerScience"
    />
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
          A: "Barometer",
          B: "Hydrometer",
          C: "Hygrometer",
          D: "Lactometer",
        },
        {
          id: 2,
          question: "The shape of our milky way galaxy is:",
          Answer: "spiral",
          A: "circular",
          B: "elliptical",
          C: "spiral",
          D: "None of the above",
        },
        {
          id: 3,
          question:
            "The different colours of different stars are due to the variation of:",
          Answer: "temperature",
          A: "temperature",
          B: "pressure",
          C: "density",
          D: "radiation from them",
        },
        {
          id: 4,
          question:
            "The fundamental scientific principle in the operation of a battery is:",
          Answer: "dissociation of electrolytes",
          A: "acid-base interaction",
          B: "dialysis",
          C: "dissociation of electrolytes",
          D: "oxidation-reduction",
        },
        {
          id: 5,
          question:
            "Instrument used to measure the force and velocity of the wind is:",
          Answer: "Anemometer",
          A: "Ammeter",
          B: "Anemometer",
          C: "Altimeter",
          D: "Audiometer",
        },
        {
          id: 6,
          question:
            "Which combination of colours is the most convenient during day and night time?",
          Answer: "White and black",
          A: "Organe and blue",
          B: "White and black",
          C: "Yellow and blue",
          D: "Red and green",
        },
        {
          id: 7,
          question: "Woolen clothes keep the body warm because:",
          Answer: "Wool is a bad conductor",
          A: "Wool increases the temperature of the body",
          B: "Wool is a bad conductor",
          C: "Wool absorbs radiant heat from outer objects",
          D: "Wool rejects heat from the outer objects",
        },
        {
          id: 8,
          question:
            "If the length of a simple pendulum is halved then its period of oscillation is:",
          Answer: "decreased by a factor",

          A: "doubled",
          B: "halved",
          C: "increased by a factor",
          D: "decreased by a factor",
        },
        {
          id: 9,
          question: "Equilibrium is a condition that can:",
          Answer: "change only if some internal factor changes.",
          A: "never change.",
          B: "change only if some external factor changes.",
          C: "change only if some internal factor changes.",
          D: "change only if government policies change.",
        },
        {
          id: 10,
          question:
            "While catching a ball, a player pulls down his hands to lower the:",
          Answer: "momentum",
          A: "force",
          B: "momentum",
          C: "impulse",
          D: "catching time",
        },
      ],
      ChemistryQuiz: [
        {
          id: 1,
          question:
            "The alloy steel containing chromium to resist rusting is known as stainless steel. What is played by Chromium in stainless steel? 1.Chromium does not rust, so it works as protecting cover. 2. Chromium reacts with Iron to make a compound that is not affected by Oxygen Select the correct option from the codes given below:",
          Answer: "Neither 1 nor 2",
          A: "Only 1",
          B: "Only 2",
          C: "Both 1 & 2",
          D: "Neither 1 nor 2",
        },
        {
          id: 2,
          question:
            "Which of the following chemicals is also known as lachrymatory agent or lachrymator? ",
          Answer: "Tear gas",
          A: "Mustard Gas",
          B: "Tear gas",
          C: "Diborane",
          D: "Chlorine gas",
        },
        {
          id: 3,
          question:
            "Which of the following chemicals is also known as butter of tin ?",
          Answer: "Stannic chloride",
          A: "Stannic chloride",
          B: "Sodium perborate",
          C: "Potassium nitrate",
          D: "Magnesium hydroxide",
        },
        {
          id: 4,
          question:
            "Which of the following states of matter has the weakest Intermolecular forces?",
          Answer: "Gases",
          A: "Solids",
          B: "Liquids",
          C: "Gases",
          D: "It is same in solids, liquids and gases",
        },
        {
          id: 5,
          question:
            "What is the maximum stress after which the wire breaks called as?",
          Answer: "Tensile strength",
          A: "Tensile strength",
          B: "Shear strength",
          C: "Bulk strength",
          D: "Hooke’s strength",
        },
        {
          id: 6,
          question:
            "What can be the maximum number of electrons in a shell, if principal quantum number is n?",
          Answer: "2n2",
          A: "n",
          B: "n2",
          C: "2n2",
          D: "3n3",
        },
        {
          id: 7,
          question:
            "Which of the following equation represents combination of Hydrogen gas with nitrogen to form ammonia?",
          Answer: "3H2 + N2 –> 2NH3",
          A: "2H2 + N –> NH3",
          B: "2H + N3 –> NH3",
          C: "3H2 + N2 –> 2NH3",
          D: "None of the above",
        },
        {
          id: 8,
          question: "What of these is the chemical formula of Rust?",
          Answer: "",
          A: "Fe2O3. nH2O",
          B: "Fe2Cl3. nH2O",
          C: "FeCO2. nH2O",
          D: "FeO. nH2O",
        },
        {
          id: 9,
          question:
            "The Lanthanoids are part of which of the following block of elements in the periodic table?",
          Answer: "f-block",
          A: "p-block",
          B: "s-block",
          C: "d-block",
          D: "f-block",
        },
        {
          id: 10,
          question: "Choose the incorrect statement:",
          Answer: "Epsom salt is an ore containing Sodium",
          A: "Epsom salt is an ore containing Sodium",
          B: "Bauxite is an ore of Aluminium",
          C: "Asbestos is an ore containing Calcium",
          D: "Milarite mineral contains Nickel",
        },
      ],
      computerScience: [
        {
          id: 1,
          question: "What is a data structure?",
          Answer: "A way to store and organize data",
          A: "A programming language",
          B: "A collection of algorithms",
          C: "A way to store and organize data",
          D: "A type of computer hardware",
        },
        {
          id: 2,
          question: "What are the disadvantages of arrays?",
          Answer: "There are chances of wastage of memory space if elements inserted in an array are lesser than the allocated size",
          A: "Index value of an array can be negative",
          B: "Elements are sequentially accessed",
          C: "Data structure like queue or stack cannot be implemented",
          D: "There are chances of wastage of memory space if elements inserted in an array are lesser than the allocated size",
        },
        {
          id: 3,
          question: " Which data structure is used for implementing recursion?",
          Answer: "Stack",
          A: "Stack",
          B: "Queue",
          C: "List",
          D: "Array",
        },
        {
          id: 4,
          question: "The data structure required to check whether an expression contains a balanced parenthesis is?",
          Answer: "Stack",
          A: "Queue",
          B: "Stack",
          C: "Tree",
          D: "Array",
        },
        {
          id: 5,
          question: " Which of the following is not the application of stack?",
          Answer: "",
          A: "Data Transfer between two asynchronous process",
          B: "Compiler Syntax Analyzer",
          C: "Tracking of local variables at run time",
          D: "A parentheses balancing program",
        },
        {
          id: 6,
          question: "Which data structure is needed to convert infix notation to postfix notation?",
          Answer: "Stack",
          A: "Tree",
          B: "Branch",
          C: "Stack",
          D: "Queue",
        },
        {
          id: 7,
          question: "What data structure would you mostly likely see in non recursive implementation of a recursive algorithm?",
          Answer: "Stack",
          A: "Stack",
          B: "Linked List",
          C: "Tree",
          D: "Queue",
        },
        {
          id: 8,
          question: "What is the value of the postfix expression 6 3 2 4 + – *?",
          Answer: "-18",
          A: "74",
          B: "-18",
          C: "22",
          D: "40",
        },
        {
          id: 9,
          question: "Which of the following statement(s) about stack data structure is/are NOT correct?",
          Answer: "Stack is the FIFO data structure",
          A: "Top of the Stack always contain the new node",
          B: "Stack is the FIFO data structure",
          C: "Null link is present in the last node at the bottom of the stack",
          D: "Linked List are used for implementing Stacks",
        },
        {
          id: 10,
          question: "The data structure required for Breadth First Traversal on a graph is?",
          Answer: "Queue",
          A: "Array",
          B: "Stack",
          C: "Tree",
          D: "Queue",
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
