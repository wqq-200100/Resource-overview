<template>
  <!-- 基础平台表格 -->
  <div class="main-table">
    <div class="left">
      <myMeter/>
    </div>

    <div class="center">
      <div class="label-title">存储</div>
      <div class="imgUrl" v-for="item in image">
        <img :src=item alt="" class="imgIcon">
      </div>
      <column :datas="datas" class="colum"/>
    </div>


    <div class="c">
      <div class="label-title">网络</div>
    </div>
  </div>
</template>

<script setup>
import myMeter from "../../../global/meter.vue";
import column from "../../../global/column.vue";

import img1 from "../../../assets/image/img1.png";
import img2 from "../../../assets/image/img2.png";
import img3 from "../../../assets/image/img3.png";
import img4 from "../../../assets/image/img4.png";



const datas = $ref([
  { name: "SSD存储", value: "264" },
  { name: "FC存储", value: "241" },
  { name: "分布式存储", value: "312" },
  { name: "视频云存储", value: "447" },
])


const image = $ref([img1, img2, img3, img4])

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
    position: relative;


    .colum {
      width: 95%;
      height: 100px;
      margin: 5px auto;
    }

    .imgUrl {
      margin: 12px 25px 0;

      .imgIcon {
        width: 35px;
      }
    }

    .colum {
      position: absolute;
      top: 0;
      left: 60px;
      margin-top: 10px;
      height: 235px;
    }
  }


  .c {
    width: 32%;
    border: 1px solid rgb(51, 102, 140);

  }

}
</style>
