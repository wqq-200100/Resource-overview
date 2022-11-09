<template>
  <!-- 柱状图 -->
  <div ref="myChartRef" style="width: 100%;height: 100px"></div>
</template>

<script setup>
import {onMounted} from "vue";
import * as echarts from 'echarts'

let myChart = null
const myChartRef = $ref()

const props = defineProps({
  category:[],
  total:[]
})

// const category = [
//   {name: 'SSD存储', value: 123},
//   {name: '分布式存储', value: 108},
// ]; // 类别

const category = props.category

const total = props.total; // 数据总数
const a = ['20%', '40%', '60%', '80%', '100%'];
var datas = [];
category.forEach((value) => {
  datas.push(value.value);
});
const ydata = category.map((v) => v.name);
const option = {
  grid: {
    left: '10%',
    top: '8%', // 设置条形图的边距
    right: '18%',
    bottom: '10%',
  },
  xAxis: {
    splitLine: {
      show: false,
      lineStyle: {
        color: 'rgba(255,255,255,0.2)',
        type: 'dashed',
      },
    },
    axisLine: {
      show: false,
    },
    axisLabel: {
      show: false,
      color: '#ABBFE3',
    },
    axisTick: {
      show: false,
    },
  },
  yAxis: [
    {
      type: 'category',
      inverse: true,
      data: ydata,
      axisLine: {
        show: false,
      },
      axisTick: {
        show: false,
      },
      axisLabel: {
        show: true,
        textStyle: {
          verticalAlign: 'bottom',
          color: '#299CD4',
          fontSize: 14,
          fontFamily: 'Microsoft YaHei',
          align: 'left',
          padding: [0, 0, 10, 10],
        },
        formatter: (name, index) => {
          const _index = index + 1;
          if (index == 0) {
            return `${name}`;
          }
          return `${name}`
        },
      },
      offset: 0,
    },
  ],
  series: [
    {
      // 内
      type: 'bar',
      barWidth: 14,
      barCateGoryGap: 20,
      legendHoverLink: false,
      silent: true,
      itemStyle: {
        normal: {
          barBorderRadius: 10,
          color: function (params) {
            var color;
            if (params.dataIndex == 0) {
              color = {
                type: 'linear',
                x: 0,
                y: 0,
                x2: 1,
                y2: 0,
                colorStops: [
                  {
                    offset: 0,

                    color: '#2abeb9', // 0% 处的颜色
                  },
                  {
                    offset: 1,
                    color: '#168380', // 100% 处的颜色
                  },
                ],
              };
            } else if (params.dataIndex == 1) {
              color = {
                type: 'linear',
                x: 0,
                y: 0,
                x2: 1,
                y2: 0,
                colorStops: [
                  {
                    offset: 0,

                    color: '#FFAF04', // 0% 处的颜色
                  },
                  {
                    offset: 1,
                    color: '#9f6e05', // 100% 处的颜色
                  },
                ],
              };
            } else if (params.dataIndex == 2) {
              color = {
                type: 'linear',
                x: 0,
                y: 0,
                x2: 1,
                y2: 0,
                colorStops: [
                  {
                    offset: 0,

                    color: '#FFF600', // 0% 处的颜色
                  },
                  {
                    offset: 1,
                    color: '#FFF600', // 100% 处的颜色
                  },
                ],
              };

            } else {
              color = {
                type: 'linear',
                x: 0,
                y: 0,
                x2: 1,
                y2: 0,
                colorStops: [
                  {
                    offset: 0,
                    color: '#299CD4', // 0% 处的颜色
                  },
                  {
                    offset: 1,
                    color: '#299CD4', // 100% 处的颜色
                  },
                ],
              };
            }
            return color;
          },
        },
      },
      label: {
        normal: {
          show: false,
          position: '[0, 0, 15, 10]',
          formatter: '{b}',
          textStyle: {
            color: '#fff',
            fontSize: 14,
          },
        },
      },
      data: category,
      z: 2,
      animationEasing: 'elasticOut',
    },
    {
      // 外边框
      type: 'pictorialBar',
      symbol: 'rect',
      symbolBoundingData: total,
      itemStyle: {
        barBorderRadius: 10,
        normal: {
          color: 'none',
        },
      },
      label: {
        normal: {
          padding: [0, 10, 0, 10],
          formatter: (params) => {
            var text = '{d| ' + params.data + '}{f|   ' + (params.data / total) * 100 + '%}';
            return text;
          },
          rich: {
            a: {
              color: '#D5E9FF',
            },
            b: {
              color: '#D5E9FF',
            },
            c: {
              color: '#D5E9FF',
            },
            d: {
              color: '#D5E9FF',
            },
            f: {
              color: '##D5E9FF',
            },
          },
          position: 'right',
          distance: 1, // 向右偏移位置
          show: true,
        },
      },
      data: datas,
      z: 0,
      animationEasing: 'elasticOut',
    },
    {
      name: '外框',
      type: 'bar',
      barCateGoryGap: 20,
      barGap: '-100%', // 设置外框粗细
      data: [
        total,
        total,
        total,
        total,
        total,
        total,
        total,
        total,
        total,
        total,
      ],
      barWidth: 14,
      itemStyle: {
        normal: {
          color: '#2b2b3a', // 填充色
          barBorderColor: '#999', // 边框色
          barBorderWidth: 0.1, // 边框宽度
          barBorderRadius: 10, //圆角半径
          label: {
            // 标签显示位置
            show: false,
            position: 'top', // insideTop 或者横向的 insideLeft
          },
        },
      },
      z: 0,
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
