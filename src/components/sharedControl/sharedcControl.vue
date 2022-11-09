<template>
  <div class="sharedControl">
    <div class="label-title">成都市政务信息资源共享应用管理平台（独占）</div>

    <div class="sharedControl-chart">
      <div class="pie">
        <!--服务器-->
        <div class="pri">
          <div class="pri-left" v-for="item in circleData">
            <div class="system-title">{{ item.title }}</div>
            <div class="pri-box">
              <myCircle :color="item.color"
                        :total="item.total"
                        :value="item.value"
                        :sum="item.sum"
                        class="myCircle"/>
              <div class="box-center">
                <div class="play">运行中 <span>{{ item.value }}</span></div>
                <div class="size">磁盘大小 <span>{{ item.size }}TB</span></div>
              </div>
              <div class="box-right">
                <div class="stop">已停止 <span style="color: red">{{ item.stop }}</span></div>
                <div class="mirrorImage">镜像 <span>{{ item.mirrorImage }}个</span></div>
              </div>
            </div>
          </div>
        </div>
        <!--存储-->
        <div class="storage">
          <div class="system-title">存储</div>
          <div style="display: flex;justify-content: space-between;">
            <myStorage :category="category1" :total="total1"/>
            <myStorage :category="category2" :total="total2"/>
          </div>
        </div>
      </div>
      <!--利用率&峰值-->
      <div class="foldLine">
        <foldLine style="margin-left: 40px"/>
      </div>
    </div>
  </div>
</template>

<script setup>
import myCircle from "../../global/circle.vue";
import myColumn from "../../global/column.vue";
import myStorage from "../../global/myStorage.vue";
import foldLine from "./foldLine.vue";


const circleData = $ref([
  {title: '云服务器ESC', color: 'yellow', total: 99, value: 99, sum: 99, stop: 0, size: 23, mirrorImage: 182},
  {title: '裸金属服务器', color: 'orange', total: 200, value: 130, sum: 200, stop: 0, size: 0, mirrorImage: 0},
])

const category1 = $ref([
  {name: "SSD存储", value: "22"},
  {name: "分布式存储", value: "99"},
])
const category2 = $ref([
  {name: "FC存储", value: "33"},
  {name: "视频云存储", value: "12"},
])

const total1 = $ref(200)
const total2 = $ref(150)


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
    justify-content: space-around;

    .pie {
      width: 49%;

      .pri {
        display: flex;
        justify-content: space-around;
        margin-top: 10px;

        .pri-left, .pri-right {
          width: 49%;
          height: 185px;
          border: 1px solid rgb(51, 102, 140);
        }

        .pri-box {
          width: 100%;
          height: 130px;
          display: flex;
          line-height: 60px;
          justify-content: space-around;
          align-items: center;

          span {
            color: orange;
          }

          .myCircle {
            width: 150px;
            height: 150px;
          }
        }
      }

      .storage {
        width: 99%;
        height: 130px;
        margin: 10px auto;
        border: 1px solid rgb(51, 102, 140);

        .aa {
          width: 150px;
        }
      }
    }

    .foldLine {
      width: 49%;
      height: 95%;
      border: 1px solid rgb(51, 102, 140);
      margin-top: 11px;
    }
  }

}
</style>
