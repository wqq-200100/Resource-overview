<template>
  <div class="systemTable">
    <div class="tableHead">
      <div class="label-title">上云系统</div>
      <div class="search">
        <el-input
            v-model="input3"
            class="w-50 m-2"
            size="default"
            placeholder="请输入内容"
            :suffix-icon="Search"
            background="red"
        />
      </div>
    </div>
    <div class="from">
      <div class="from-left">
        <el-table :data="tableData" style="width: 100%">
          <el-table-column prop="name" label="云服务商"/>
          <el-table-column prop="system" label="系统"/>
          <el-table-column prop="cpu" label="CPU(核)"/>
          <el-table-column prop="memory" label="内存（G）"/>
          <el-table-column prop="storage" label="存储（G）"/>
          <el-table-column prop="time" label="上云时间"/>
        </el-table>
      </div>
      <div class="from-right">
        <el-table :data="tableData" style="width: 100%">
          <el-table-column prop="name" label="云服务商"/>
          <el-table-column prop="system" label="系统"/>
          <el-table-column prop="cpu" label="CPU(核)"/>
          <el-table-column prop="memory" label="内存（G）"/>
          <el-table-column prop="storage" label="存储（G）"/>
          <el-table-column prop="time" label="上云时间"/>
        </el-table>
      </div>
    </div>
  </div>
</template>

<script setup>
import {Search} from '@element-plus/icons-vue'

const input3 = $ref('')

const tableData = [
  {
    name: '新华三云',
    system: '成都市公车网系统',
    cpu: '40',
    memory: '919',
    storage: '2841',
    time: '2020/1/9'
  },
  {
    name: '新华三云',
    system: '成都市公车网系统',
    cpu: '40',
    memory: '919',
    storage: '2841',
    time: '2020/1/9'
  },
  {
    name: '新华三云',
    system: '成都市公车网系统',
    cpu: '40',
    memory: '919',
    storage: '2841',
    time: '2020/1/9'
  },
  {
    name: '新华三云',
    system: '成都市公车网系统',
    cpu: '40',
    memory: '919',
    storage: '2841',
    time: '2020/1/9'
  },
  {
    name: '新华三云',
    system: '成都市公车网系统',
    cpu: '40',
    memory: '919',
    storage: '2841',
    time: '2020/1/9'
  },
]
</script>

<style scoped lang="scss">
.systemTable {
  width: 100%;
  height: 223px;
  margin-top: 8px;
  border: 1px solid rgb(51, 102, 140);

  .tableHead {
    width: 20%;
    display: flex;
    justify-content: center;

    .search {
      width: 170px;

      ::v-deep(.el-input__wrapper) {
        background: rgb(11, 43, 57);
        box-shadow: 0 0 0;
        border: 1px solid rgb(28, 66, 91);
        height: 25px;
      }
    }
  }

  .from {
    display: flex;
    justify-content: space-around;

    .from-left, .from-right {
      width: 49%;
      height: 190px;
      margin-top: 3px;
      border: 1px solid rgb(51, 102, 140);
      overflow: scroll;
      overflow-x: hidden;

      ::v-deep(.el-table:not(.el-table--border) .el-table__cell) {
        background: rgb(0, 62, 90);
      }

      ::v-deep(.el-table td.el-table__cell, .el-table th.el-table__cell.is-leaf) {
        background: rgb(14, 44, 63) !important;
      }


      ::v-deep(.el-table tr) {
        color: #fff;
      }

      ::v-deep(.el-table) {
        --el-table-border-color: rgb(0, 62, 90)
      }

      ::v-deep(.el-table--enable-row-hover .el-table__body tr:hover>td.el-table__cell) {
        background-color: rgb(0, 62, 92);
      }
    }
  }
}
</style>
