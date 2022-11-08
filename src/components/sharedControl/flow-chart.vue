<template>
<!--流量风气值折线图-->
  <div ref="myChartRef" class="tubiao"></div>
</template>

<script setup >
import * as echarts from 'echarts';
import {onMounted} from "vue";

let myChart = null;
let myChartRef = $ref();

let result = [{ name: "03-31", ai: 800, ai2: 489 },
  { name: "04-01", ai: 676, ai2: 288 },
  { name: "04-02", ai: 777, ai2: 177 },
  { name: "04-03", ai: 878, ai2: 487 },
  { name: "04-04", ai: 768, ai2: 277 },
  { name: "04-05", ai: 777, ai2: 387 },
  { name: "04-06", ai: 888, ai2: 478 }]

let xData = result.map((item) => { return item.name });
let keys = ['ai', 'ai2'], seriesData = [];
keys.forEach((key) => {
  seriesData.push({
    "name": key + "数",
    "data": result.map((item) => { return item[key] }),
    "type": "line",
    "yAxisIndex": 0,
    "symbol": "none",
    "symbolSize": 7,
    "barWidth": 14,
    "splitNumber": 6,
    "smooth": false,
    "itemStyle":
        {
          "color": "rgb(0, 254, 210)"
        },
    "lineStyle":
        {
          "color": "rgb(0, 254, 210)",
          "width": 1
        },
    "areaStyle":
        {
          "opacity": 1,
          "color":
              {
                "x": 0,
                "y": 0,
                "x2": 0,
                "y2": 1,
                "type": "linear",
                "global": false,
                "colorStops": [
                  {
                    "offset": 0,
                    "color": "rgba(0, 254, 210,0.35)"
                  },
                  {
                    "offset": 0.8,
                    "color": "rgba(6, 8, 41,.1)"
                  }]
              },
          "shadowColor": "rgba(0, 0, 0, 0.1)",
          "shadowBlur": 10
        }
  })
  seriesData.push({
    "name": key + "数",
    "data": [{
      "coords": result.map((item) => { return [item.name, item[key]] }),
    }],
    "type": "lines",
    "coordinateSystem": "cartesian2d",
    "zlevel": 1,
    "polyline": true,
    "smooth": true,
    "symbol": "circle",
    "effect":
        {
          "show": true,
          "trailLength": 0.4,
          "symbol": "circle",
          "period": 8,
          "symbolSize": 8
        },
    "lineStyle":
        {
          "normal":
              {
                "color": "rgba(0, 254, 210,1)",
                "width": 0,
                "opacity": 0,
                "curveness": 0
              }
        }
  })
})

const option = {
  backgroundColor: '',
  "grid":
      {
        "show": true,
        "top": 50,
        "left": 20,
        "right": 30,
        "bottom": 36,
        "containLabel": true,
        "borderWidth": 0,
        "backgroundColor": "rgba(12, 45, 81, .3)"
      },
  "legend":
      {
        "show": false,
        "top": 0,
        "right": 30,
        "itemWidth": 14,
        "itemHeight": 2,
        "itemGap": 24,
        "icon": "react",
        "textStyle":
            {
              "padding": [0, 0, 0, 4],
              "fontSize": 15,
              "color": "#fff"
            }
      },
  "dataZoom": [
    {
      "type": "inside",
      "dataBackground": "#0ff",
      "showDetail": false
    }],
  "xAxis":
      {
        "type": "category",
        "boundaryGap": false,
        "data": xData,
        "axisPointer":
            {
              "handle":
                  {
                    "show": false
                  }
            },
        "axisLine":
            {
              "show": false,
              "lineStyle":
                  {
                    "color": "#AEC6DF"
                  }
            },
        "axisTick":
            {
              "show": false
            }
      },
  "yAxis": [
    {
      "show": true,
      "nameGap": 0,
      "type": "value",
      "minInterval": 1,
      "splitLine":
          {
            "show": false
          },
      "axisTick":
          {
            "show": false
          },
      "minorSplitLine":
          {
            "show": false
          },
      "axisLine":
          {
            "show": false
          },
      "nameTextStyle":
          {
            "fontSize": 14,
            "padding": [0, 0, 0, -15],
            "align": "left",
            "color": "#AEC6DF;"
          },
      "axisLabel":
          {
            "color": "#AEC6DF"
          }
    }],
  "series": seriesData
}

onMounted(() => {
  myChart = echarts.init(myChartRef)
  myChart.setOption(option);
})


</script>

<style lang='scss' scoped>
.tubiao{
  width: 100%;
  height: 180px;
  margin-top: -40px;
}
</style>
