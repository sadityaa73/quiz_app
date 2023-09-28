<template>
  <MainContainer />
</template>

<script>
import MainContainer from "./components/Main/MainContainer.vue";
export default {
  name: "App",
  components: {
    MainContainer,
  },
};
</script>

<style>
#app {
  display: flex;
  min-width: 70%;
  min-height: 100vh;
  justify-content: center;
  align-items: center;
}
</style>
