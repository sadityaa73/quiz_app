<template>
  <div class="main-container">
    <div class="container-one">
      <div class="question-container"></div>
      <div class="answer-container"></div>
      <div class="btn-container">
        <button class="previous-btn">previous & save</button
        ><button class="next-btn">next & save</button>
      </div>
    </div>
    <div class="container-two">
     <div class="table-of-question"></div>
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
  margin: 7px;
  max-width: 100%;
  min-height: 55px;
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
}
.btn-container {
  margin: 7px;
  min-height: 36px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.previous-btn {
  margin-left: 6px;
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
.container-two{
  border: 1px solid;
  margin: 7px;
  margin-top: 10px;
  width: 35%;
  min-height: 55px;
  border-radius: 6px;
  background: white;
}
.table-of-question{
  border: 1px solid;
  margin: 5px;
  min-height: 250px;
  display: flex;
  justify-content: flex-start;
  align-items: flex-start;
  flex-wrap: nowrap;
}
</style>
