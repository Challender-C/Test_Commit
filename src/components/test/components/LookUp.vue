<template>
  <div>
    <el-dialog
  title="提示"
  :visible.sync="dialogVisible"
  width="30%"
  :before-close="close_top"
  style="margin-top:-10vh">
  <el-descriptions title="用户信息">
    <el-descriptions-item label="时间">{{userInfo.date}}</el-descriptions-item>
    <el-descriptions-item label="姓名">{{userInfo.name}}</el-descriptions-item>
    <el-descriptions-item label="省份">{{userInfo.province}}</el-descriptions-item>
    <el-descriptions-item label="市区">{{userInfo.city}}</el-descriptions-item>
    <el-descriptions-item label="地址">{{userInfo.address}}</el-descriptions-item>
    <el-descriptions-item label="邮编">{{userInfo.zip}}</el-descriptions-item>
</el-descriptions>
  <div slot="footer" class="dialog-footer">
    <el-button @click="close_top">取 消</el-button>
    <el-button type="primary" @click="close_top">确 定</el-button>
  </div>
</el-dialog>
  </div>
</template>

<script>
  export default {
    props: {
      userInfo:{
        type:Object
      }
    },
   data() {
      return {
        dialogVisible: true,
      };
    },
    methods: {
      close_top(){
        this.dialogVisible = !this.dialogVisible
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>