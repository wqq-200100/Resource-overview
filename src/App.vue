<template>
  <div class="header">
    <dv-decoration8 style="width:500px;height:40px;"/>
    <div>部门资源概览</div>
    <dv-decoration8 :reverse="true" style="width:500px;height:40px;"/>
  </div>

  <div class="box">
    <fromFlex/>

    <systemTable/>

    <sharedControl/>
  </div>

</template>

<script setup>
import fromFlex from "./components/fromFlex/fromFlex.vue";
import systemTable from "./components/systemTable/systemTable.vue";
import sharedControl from "./components/sharedControl/sharedcControl.vue";

</script>

<style scoped lang="scss">
.header {
  width: 100%;
  height: 75px;
  border: 1px solid rgb(51, 102, 140);
  color: #fff;
  text-align: center;
  font-size: 35px;
  font-weight: 500;
  line-height: 75px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: rgb(12, 35, 52);

  div {
    margin: 0 40px;
  }
}

</style>
