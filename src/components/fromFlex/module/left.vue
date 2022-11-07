<template>
  <!-- 基础平台表格 -->
  <div class="main-table">
    <div class="left">
      <myMeter/>
    </div>

    <div class="center">
      <div class="label-title">存储</div>
<!--      <column class="colum" />-->
    </div>
    <div class="c">
      <div class="label-title">网络</div>
    </div>
  </div>
</template>

<script setup>
import myMeter from "../../../global/meter.vue";
import column from "../../../global/column.vue";


</script>

<style scoped lang="scss">
.main-table {
  display: flex;
  justify-content: space-between;
  width: 100%;
  height: 240px;

  .left {
    width: 32%;
    border: 1px solid rgb(51, 102, 140);

  }

  .center {
    width: 32%;
    border: 1px solid rgb(51, 102, 140);

    .colum{
      width: 95%;
      height: 100%;
      margin: 5px auto;
    }
  }

  .c {
    width: 32%;
    border: 1px solid rgb(51, 102, 140);

  }

}
</style>
