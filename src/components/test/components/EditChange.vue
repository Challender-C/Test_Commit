<template>
  <div>
    <el-dialog
  title="提示"
  :visible.sync="dialogVisible"
  width="30%"
  :before-close="close_top"
  style="margin-top:-10vh">
   <el-form :model="form">
    <el-form-item label="日期">
      <el-input autocomplete="off" :value="userInfo.date"></el-input>
    </el-form-item>
     <el-form-item label="姓名">
      <el-input autocomplete="off" v-model="userInfo.name"></el-input>
    </el-form-item>
     <el-form-item label="省份">
      <el-input autocomplete="off" v-model="userInfo.province"></el-input>
    </el-form-item>
     <el-form-item label="市区">
      <el-input autocomplete="off" v-model="userInfo.city"></el-input>
    </el-form-item>
     <el-form-item label="地址">
      <el-input autocomplete="off" v-model="userInfo.address"></el-input>
    </el-form-item>
     <el-form-item label="邮编">
      <el-input autocomplete="off" v-model="userInfo.zip"></el-input>
    </el-form-item>
  </el-form>
  <div slot="footer" class="dialog-footer">
    <el-button @click="close_top">取 消</el-button>
    <el-button type="primary" @click="handleClose">确 定</el-button>
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
        info:{
          date:'',
          name:'',
          province:'',
          city:'',
          address:'',
          zip:''
        }
      };
    },
    methods: {
      close_top(){
        this.dialogVisible = false
      },
      handleClose(done) {
        this.$confirm('确认保存？')
          .then(_ => {
            this.dialogVisible = false
            userInfo = this.info
          })
          .catch(_ => {});
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>