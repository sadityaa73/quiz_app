<template>
  <div id="main">
    <NavigationBar/>
    <HomeSection v-if="!isPhysicsQuiz && !isChemistryQuiz && !isComputerScienceQuiz && !isStart" @subjectName="getSubjectName"/>
    <GeneralNote v-if="isStart" :subjectName="subject" @subject="startQuiz"/>
    <PhysicsQuiz v-if="isPhysicsQuiz" :subjectName = "subject"/>
    <ChemistryQuiz v-if="isChemistryQuiz" :subjectName = "subject"/>
    <ComputerScienceQuiz v-if="isComputerScienceQuiz" :subjectName = "subject"/>
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
        subject:""
    };
  },
  methods:{
    getSubjectName(event){
        this.subject = event;
        this.isStart = event;
    },
    startQuiz(event){
        if(event === "physics")
        {
            this.isStart =  false;
            this.isPhysicsQuiz = true;
        }else if(event === "chemistry")
        {
            this.isStart =  false;
            this.isChemistryQuiz = true;
        }
        else{
            this.isStart =  false;
            this.isComputerScienceQuiz = true;
        }
    }
  }
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
