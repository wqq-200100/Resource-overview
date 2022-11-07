<template>
  <div class="topBox">
    <div class="server-title">
      <div class="label-title">云服务器ECS</div>
      <div class="label-title">裸金属服务器</div>
    </div>
    <div class="meter">
      <!--   仪表盘左边   -->
      <Dashboard class="dashboard" :data-value="dataValue1"/>
      <div class="left-data">
        <div class="Stopped">
          <div class="num">0台</div>
          <div>已停止</div>
        </div>
        <div class="afoot">
          <div class="num">4615台</div>
          <div>运行中</div>
        </div>
      </div>

      <!--   仪表盘右边   -->
      <Dashboard class="dashboard" :data-value="dataValue2"/>
      <div class="right-data">
        <div class="Stopped">
          <div class="num">0台</div>
          <div>已停止</div>
        </div>
        <div class="afoot">
          <div class="num">2台</div>
          <div>运行中</div>
        </div>
      </div>
    </div>

    <!--仪表盘下面的数据-->
    <div class="memory">
      <div class="cpuNum">
        <div class="mg">
          <div class="num">266TB</div>
          <div class="textColor">硬盘大小</div>
        </div>
        <div>
          <div class="num">4615个</div>
          <div class="textColor">镜像</div>
        </div>
      </div>
      <div class="cpuNum">
        <div class="mg">
          <div class="num">22TB</div>
          <div class="textColor">硬盘大小</div>
        </div>
        <div>
          <div class="num">59个</div>
          <div class="textColor">操作系统</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Dashboard from "./Dashboard.vue";


let dataValue1 = $ref(99)
let dataValue2 = $ref(67)
</script>

<style scoped lang='scss'>
.topBox {
  width: 100%;

  .server-title {
    display: flex;
  }

  .meter {
    display: flex;
    justify-content: space-around;

    .dashboard {
      width: 120px;
      height: 145px;
    }

    .left-data, .right-data {
      font-size: 16px;
      display: flex;
      flex-direction: column-reverse;
      justify-content: space-around;
    }
  }

  .memory {
    display: flex;
    justify-content: space-around;

    .cpuNum {
      display: flex;
      margin-right: 30px;

      .mg {
        margin-right: 80px;
      }

      .textColor {
        color: rgb(1, 299, 233);
      }
    }
  }

  .num {
    color: rgb(61, 175, 96);
  }

}
</style>
