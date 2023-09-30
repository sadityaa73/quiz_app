<template>
  <div id="main">
    <NavigationBar/>
    <HomeSection v-if="!isPhysicsQuiz && !isChemistryQuiz && !isComputerScienceQuiz" />
    <GeneralNote v-if="isStart"/>
    <PhysicsQuiz v-if="isPhysicsQuiz"/>
    <ChemistryQuiz v-if="isChemistryQuiz"/>
    <ComputerScienceQuiz v-if="isComputerScienceQuiz"/>
  </div>
</template>
<script>
import HomeSection from '../HomeSection/HomeSection.vue';
import NavigationBar from '../Navigation/NavigationBar.vue';
import GeneralNote from "../GeneralNote/GeneralNote.vue";
import PhysicsQuiz from "../SubjectQuiz/PhysicsQuiz.vue";
import ChemistryQuiz from "../SubjectQuiz/ChemistryQuiz.vue";
import ComputerScienceQuiz from "../SubjectQuiz/ComputerScience.vue"
export default {
    components:{NavigationBar,HomeSection,GeneralNote,PhysicsQuiz,ChemistryQuiz,ComputerScienceQuiz},
  data() {
    return {
        isStart:false,
        isPhysicsQuiz:false,
        isChemistryQuiz:false,
        isComputerScienceQuiz:false,
    };
  },
};
</script>
<style scoped>
#main{
    display: flex;
    justify-content: flex-start;
    align-items: flex-start;
    width: 100%;
    border: 1px solid green;
    border-radius: 7px;
    background: #f1f5f4;
}
</style>
