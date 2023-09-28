<template>
  <div id="main">
    <NavigationBar/>
    <HomeSection/>
  </div>
</template>
<script>
import HomeSection from '../HomeSection/HomeSection.vue';
import NavigationBar from '../Navigation/NavigationBar.vue';
export default {
    components:{NavigationBar,HomeSection,},
  data() {
    return {};
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
