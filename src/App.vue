<template>
  <div class="header">部门资源概览</div>
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
  border: 1px solid rgb(51,102,140);
  color: #fff;
  text-align: center;
  font-size: 26px;
  line-height: 75px;
}

</style>
