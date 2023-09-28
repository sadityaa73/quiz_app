<template>
  <div id="navigation">
    <div class="navigation_item">
        <img src="../../assets/icons8-home-60.png" alt="Home">
    </div>
    <div class="navigation_item">
        <img src="../../assets/icons8-database-administrator-60.png" alt="admin">
    </div>
    <div class="navigation_item">
        <img src="../../assets/icons8-exit-60.png" alt="exit">
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },
};
</script>
<style scoped>
#navigation {
    border-radius: 5px;
    min-width: 66px;
    min-height: 49vh;
    margin: 1%;
    box-shadow: 1px 3px 8px 3px grey;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
}
.navigation_item{
    border-radius: 6px;
    min-width: 82%;
    min-height: 52px;
    margin: 8%;
    overflow: hidden;
}
.navigation_item:hover{
    box-shadow: 1px 3px 8px 3px grey;
    background: #2a8ff7;
}
.navigation_item:active{
    background: yellowgreen;
}
</style>
