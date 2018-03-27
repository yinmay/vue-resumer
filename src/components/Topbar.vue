<template>
  <div id="topbar">
   <div class="logo">
     VueResumer
   </div>
   <div class="actions">
     <!-- <el-button type="primary">注册</el-button>
     <el-button >登录</el-button> -->
     <el-button v-on:click="preview" type="primary" plain>预览</el-button>
   </div>
  </div>
</template>

<script>
export default {
  // name: 'Topbar',

  methods:{
    preview(){
      // alert(1)
      this.$emit('preview')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
#topbar{
  min-height:80px;
  display:flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px;
  font-size:20px;
}
</style>
