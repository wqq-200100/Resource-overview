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


    <div class="right">
      <div class="label-title">网络</div>
      <div class="myFrom">
        <div class="myFromTitle">
          <div></div>
          <div>宽带</div>
          <div>峰值</div>
          <div>IP</div>
        </div>

        <div class="myContent">
          <div class="contentName">
            <div>互联网</div>
            <div>政务外网</div>
          </div>
          <div class="num">
            <div><span style="color: rgb(217,76,76)">2</span>GB</div>
            <div><span style="color: rgb(213,134,12)">854</span>MB</div>
            <div><span style="color: rgb(224,211,78)">667</span>个</div>
            <div><span style="color: rgb(217,76,76)">65</span>GB</div>
            <div><span style="color: rgb(213,134,12)">998</span>MB</div>
            <div><span style="color: rgb(224,211,78)">560</span>个</div>
          </div>
        </div>
      </div>
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
  {name: "SSD存储", value: "264"},
  {name: "FC存储", value: "241"},
  {name: "分布式存储", value: "312"},
  {name: "视频云存储", value: "447"},
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


  .right {
    width: 32%;
    border: 1px solid rgb(51, 102, 140);

    .myFrom {
      width: 90%;
      height: 80%;
      margin: 5px auto;

      .myFromTitle {
        display: flex;
        justify-content: space-around;
        align-items: center;
        height: 25%;
        background: rgb(10, 55, 83);
        box-shadow: 5px 0 5px 2px rgb(11, 32, 45);
      }

      .myContent {
        display: flex;
        justify-content: space-between;

        .contentName {
          width: 25%;
          height: 100%;
          line-height: 76px;
          background: rgb(7, 45, 69);

          div {
            text-align: center;
          }
        }

        .num {
          width: 85%;
          height: 153px;
          display: flex;
          justify-content: space-between;
          flex-flow: wrap; /*自动换行*/
          box-shadow: -3px -5px 10px rgb(11 32 45);

          div {
            width: 33%;
            height: 49%;
            background: rgb(17, 57, 81);
            text-align: center;
            line-height: 76px;
            font-size: 14px;

            span{
              font-size: 18px;
            }
          }
        }
      }
    }
  }

}
</style>
