<template>
  <div class="sharedControl">
    <div class="label-title">成都市政务信息资源共享应用管理平台（独占）</div>

    <div class="sharedControl-chart">
      <div class="pie">
        <div class="pri">
          <div class="pri-left"></div>
          <div class="pri-right"></div>
        </div>
        <div class="storage"></div>
      </div>

      <div class="foldLine">
        <column/>
      </div>
    </div>
  </div>
</template>

<script setup>
import column from "../../global/column.vue";



</script>

<style scoped lang="scss">
.sharedControl {
  width: 100%;
  height: 360px;
  margin-top: 8px;
  border: 1px solid rgb(51, 102, 140);

  .sharedControl-chart {
    width: 100%;
    height: 95%;
    display: flex;
    justify-content: space-between;

    .pie {
      width: 49%;

      .pri {
        display: flex;
        justify-content: space-around;

        .pri-left {
          width: 49%;
          height: 185px;
          border: 1px solid rgb(51, 102, 140);
        }

        .pri-right {
          width: 49%;
          height: 185px;
          border: 1px solid rgb(51, 102, 140);
        }
      }

      .storage {
        width: 99%;
        height: 130px;
        margin: 10px auto;
        border: 1px solid rgb(51, 102, 140);
      }
    }

    .foldLine {
      width: 49%;
      border: 1px solid rgb(51, 102, 140);
    }
  }

}
</style>
