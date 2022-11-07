<template>
<div class="systemTable">
  <div class="label-title">上云系统</div>
  <div class="from">
    <div class="from-left"></div>
    <div class="from-right"></div>
  </div>
</div>
</template>

<script setup>

</script>

<style scoped lang="scss">
.systemTable{
  width: 100%;
  height: 223px;
  margin-top: 8px;
  border: 1px solid rgb(51,102,140);

  .from{
    display: flex;
    justify-content: space-around;

    .from-left{
      width: 49%;
      height: 200px;
      border: 1px solid rgb(51,102,140);
    }
    .from-right{
      width: 49%;
      height: 200px;
      border: 1px solid rgb(51,102,140);
    }
  }
}
</style>
