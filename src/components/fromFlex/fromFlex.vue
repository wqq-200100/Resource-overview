<template>
  <!-- 标题 -->
  <div class="main">
    <div class="main-title">
      <div class="title">成都市政务云基础平台</div>
      <img class="image" src="../../assets/image/xiasanjiaoxing.png" alt="">
    </div>

    <div class="main-icon">
      <!--   部门   -->
      <div class="icon">
        <img src="../../assets/image/my.png" alt="">
        <div class="department">
          <div class="department-num">96</div>
          <div class="department-name">部门</div>
        </div>
      </div>
      <!--   系统   -->
      <div class="icon">
        <img src="../../assets/image/xitong.png" alt="">
        <div class="system">
          <div class="system-num">831</div>
          <div class="system-name">系统</div>
        </div>
      </div>
    </div>
  </div>
  <!-- 图表 -->
  <left/>

</template>

<script setup>
import left from "./module/left.vue";



</script>

<style scoped lang="scss">
.main {
  display: flex;
  justify-content: space-between;

  .main-title {
    width: 300px;
    border: 1px solid rgb(51,102,140);
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 20px;

    .title{
      color: rgb(65,242,224);
    }

    .image {
      width: 30px;
    }
  }

  .main-icon {
    width: 250px;
    display: flex;
    justify-content: space-between;
    margin-right: 80px;

    .icon {
      display: flex;
      align-items: center;

      img {
        height: 35px;
        width: 35px;
      }

      .department, .system {
        margin-left: 10px;
        font-size: 14px;
      }

      .department-num {
        color: rgb(0, 170, 237);
        font-size: 20px;
      }

      .system-num {
        color: rgb(203, 147, 59);
        font-size: 20px;
      }
    }
  }
}
</style>
