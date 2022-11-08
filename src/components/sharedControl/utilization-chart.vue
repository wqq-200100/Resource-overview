<template>
<!--利用率折线图-->
  <div ref="myChartRef"  class="tubiao"></div>
</template>

<script setup >
import * as echarts from 'echarts'
import {onMounted} from "vue";

let myChart = null;
let myChartRef = $ref();
const props = defineProps({
  colors: [],
  data: [],
  name:[]
})

const option = {
  tooltip: {
    trigger: 'axis'
  },
  legend: {
    data: ['cpu利用率','内存利用率'],
    textStyle:{
      color:'#fff'
    }
  },
  grid: {
    left: '3%',
    right: '4%',
    bottom: '3%',
    containLabel: true
  },
  xAxis: {
    type: 'category',
    boundaryGap: false,
    data: ['03-31', '04-01', '04-02', '04-03', '04-04', '04-05', '04-06'],
    axisLine:{
      lineStyle:{
        color:"#fff"
      }
    }
  },
  yAxis: {
    type: 'value',
    axisLine:{
      lineStyle:{
        color:"#fff"
      }
    }
  },
  series: [
    {
      name: 'cpu利用率',
      type: 'line',
      stack: 'Total',
      data: [22, 55, 23, 43, 26, 41, 33]
    },
    {
      name: '内存利用率',
      type: 'line',
      stack: 'Total',
      data: [33, 55, 12, 9, 12, 21, 50]
    }
  ]
};

onMounted(() => {
  myChart = echarts.init(myChartRef)
  myChart.setOption(option);
})
// 使用刚指定的配置项和数据显示图表。

</script>

<style lang='scss' scoped>
.tubiao{
  width: 100%;
  height: 100%;
}

</style>
