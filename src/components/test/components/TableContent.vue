<template>
  <div>
     <el-table
    :data="tableData"
    border
    style="width: 100%"
    height='100%'>
    <el-table-column
      prop="date"
      label="日期"
      width="150">
    </el-table-column>
    <el-table-column
      prop="name"
      label="姓名"
      width="120">
    </el-table-column>
    <el-table-column
      prop="province"
      label="省份"
      width="120">
    </el-table-column>
    <el-table-column
      prop="city"
      label="市区"
      width="120">
    </el-table-column>
    <el-table-column
      prop="address"
      label="地址"
      width="838">
    </el-table-column>
    <el-table-column
      prop="zip"
      label="邮编"
      width="120">
    </el-table-column>
    <el-table-column
      label="操作"
      width="100">
      <template slot-scope="scope">
        <el-button @click="see(scope.row)" type="text" size="small">查看</el-button>
        <el-button type="text" size="small" @click="edit(scope.row)">编辑</el-button>
      </template>
    </el-table-column>
  </el-table>
  <edit-change v-if="isshow_edit" :userInfo="userInfo"></edit-change>
  <look-up v-if="isshow_look" :userInfo="userInfo"></look-up>
  </div>
</template>

<script>
import {tableData} from './data'
import EditChange from './EditChange.vue'
import LookUp from './LookUp.vue'
   export default {
     beforeMount () {
       this.tableData = tableData
     },
     components: {
       EditChange,
       LookUp
     },
     data() {
      return {
        tableData: [],
        isshow_edit:false,
        isshow_look:false,
        userInfo:{}
      }
    },
    methods: {
      handleClick(row) {
        console.log(row)
      },
      see(row){
        this.isshow_look = !this.isshow_look
        this.userInfo = row
      },
      edit(row){
        this.isshow_edit = !this.isshow_edit
        this.userInfo = row
      }
    }

    
  }
</script>

<style scoped>
 ::v-deep .el-table .cell{
  text-align: center;
}
</style>