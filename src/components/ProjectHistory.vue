<template>
  <div>
      <h2>项目经历</h2>
       <el-form >
        <div class="container" v-for="(item,index) in items">
          <el-form-item label="项目名称">
            <el-input v-model="item.school"></el-input>
          </el-form-item>
          <el-form-item label="项目内容">
            <el-input v-model="item.duration"></el-input>
          </el-form-item>
          <i class="el-icon-circle-close" v-on:click="removeItem(index)"></i>
          <hr>
        </div>
        <el-button type="primary" v-on:click="addItem">添加项目经历</el-button>
       </el-form>
  </div>
</template>
<script>
export default {
  props:['items'],
  methods:{
    addItem(){
      this.items.push( {title:'',content:''})
    },
    removeItem(index){
      this.items.splice(index,1)
    }
  }
}
</script>
