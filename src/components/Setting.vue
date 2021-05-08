<template>
  <el-card class="box-card">
    <div slot="header" class="clearfix">
      <i class="el-icon-setting card-icon"/><span id="card-title">插件配置</span>
    </div>
    <el-form ref="form" :model="form" label-width="80px">
      <el-form-item label="URL">
        <el-tooltip class="item" effect="light" content="配置Harbor私人仓库所在URL" placement="top">
          <el-input v-model="url"></el-input>
        </el-tooltip>
      </el-form-item>
      <el-form-item label="用户名">
        <el-tooltip class="item" effect="light" content="配置Harbor私人仓库用户名" placement="top">
          <el-input v-model="id"></el-input>
        </el-tooltip>
      </el-form-item>
      <el-form-item label="密码">
        <el-tooltip class="item" effect="light" content="配置Harbor私人仓库密码" placement="top">
          <el-input v-model="pwd" show-password></el-input>
        </el-tooltip>
      </el-form-item>
    </el-form>
        <el-button type="primary" @click="submit">提交</el-button>
  </el-card>
</template>

<script>
export default {
  data(){
    return {
      url: '',
      id: '',
      pwd: ''
    }
  },
  methods:{
    submit(){
      fetch('/submit',{
        method: 'POST',
        body: JSON.stringify({
          url:this.url,
          id:this.id,
          pwd:this.pwd
        })
      }).then((res)=>{
        if(res.ok)
          return res;
        else
          throw Error(res.status);
      }).then(()=>{
        this.$message({
          message: '修改成功',
          type: 'success'
        })
      }).catch((e)=>{
        this.$message({
          message: '发生错误，'+e,
          type: 'error'
        })
      })
    }
  }
}
</script>

<style scoped>
  .card-icon{
    margin-right: 1em;
  }
</style>
