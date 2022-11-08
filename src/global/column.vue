<template>
  <!-- 柱状图 -->
  <div ref="myChartRef" style="width: 85%" ></div>
</template>

<script setup>
import {onMounted} from "vue";
import * as echarts from 'echarts'

let myChart = null
const myChartRef = $ref()

const props = defineProps({
  datas:[],
})

const myColor = ["#51FC4E", "#4C5FF5", "#FFE660", "#79F1FF"].reverse();
const xData = props.datas.map((item) => item.name);
const yData = props.datas.map((item) => item.value);
const max = Math.ceil(Math.max(...yData) * 1.2);
const maxData = [max, max, max, max, max];
console.log(myColor, xData, yData, max, maxData)
const option = {
  grid: {
    left: "5%",
    right: "3%",
    bottom: "5%",
    top: "10%",
    containLabel: false,
  },
  xAxis: [
    {
      show: false,
    },
    {
      show: false,
    },
  ],
  yAxis: [
    {
      show: false,
      inverse: true,
      data: yData,
    },
    {
      show: true,
      data: yData,
      offset: -45,
      position: "right",
      axisLabel: {
        lineHeight: 0,
        verticalAlign: "bottom",
        fontSize: 15,
        color: "#4bf3f9",
        formatter: "{value}TB",
      },
      axisLine: {
        show: false,
      },
      splitLine: {
        show: false,
      },
      axisTick: {
        show: false,
      },
    },
  ],
  series: [
    {
      name: "进度",
      show: true,
      type: "bar",
      barGap: "-100%",
      xAxisIndex: 1,
      barWidth: 10,
      itemStyle: {
        borderRadius: 3,
        color: (params) => {
          var num = myColor.length;
          return {
            type: "linear",
            x: 0,
            y: 0,
            x2: 1,
            y2: 1,
            colorStops: [
              {
                offset: 0,
                color: "#0F1F45",
              },
              {
                offset: 1,
                color: myColor[params.dataIndex % num],
              },
            ],
          };
        },
      },
      // max: 0,
      labelLine: {
        show: false,
      },
      z: 2,
      data: yData,
    },
    {
      name: "外圆",
      type: "scatter",
      emphasis: {
        scale: false,
      },
      xAxisIndex: 1,
      symbolSize: 10,
      itemStyle: {
        color: (params) => {
          var num = myColor.length;
          return myColor[params.dataIndex % num];
        },
        shadowColor: "rgba(255, 255, 255, 0.5)",
        shadowBlur: 5,
        borderWidth: 1,
        opacity: 1,
      },
      z: 2,
      data: yData,
    },
    {
      name: "年份",
      z: 1,
      show: true,
      type: "bar",
      xAxisIndex: 1,
      barGap: "-100%",
      barWidth: 10,
      itemStyle: {
        borderRadius: 4,
        color: "rgba(13, 55, 78, 1)",
      },
      label: {
        show: true,
        position: [0, -25],
        // rich: {
        //   //富文本
        //   white: {
        //     //自定义颜色
        //     color: "#fff",
        //   },
        // },
        fontSize: 14,
        color: "#fff",
        formatter: function (data) {
          return xData[data.dataIndex];
        },
      },
      data: maxData,
    },
  ],
};



onMounted(() => {
  myChart = echarts.init(myChartRef)
  myChart.setOption(option)
})
</script>

<style scoped lang="scss">

</style>
