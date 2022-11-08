<template>
  <div class="footBox">
    <div class="fUtilization-title">
      <div class="system-title">利用率</div>
      <div class="zhexian-left" style="height: 160px;width: 90%">
        <utilization style="margin-top: -30px"/>
      </div>
    </div>
    <div class="flow">
      <div class="system-title">近一周峰值</div>
      <div class="zhexian-right" style="height: 150px;width: 90%;">
        <flow style="top: -80px"/>
      </div>
    </div>
  </div>
</template>

<script setup>
import utilization from "./utilization-chart.vue";
import flow from "./flow-chart.vue";

</script>

<style scoped lang='scss'>
</style>
