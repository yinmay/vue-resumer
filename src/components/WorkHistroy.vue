<template>
  <div>
      <h2>工作经历</h2>
       <el-form >
        <div class="container" v-for="(item,index) in items">
          <el-form-item label="公司">
            <el-input v-model="item.company"></el-input>
          </el-form-item>
          <el-form-item label="工作内容">
            <el-input v-model="item.content"></el-input>
          </el-form-item>
          <el-form-item label="工作时间">
            <el-input v-model="item.time"></el-input>
          </el-form-item>
          <i class="el-icon-circle-close" v-on:click="removeItem(index)"></i>
          <hr>
        </div>
        <el-button type="primary" v-on:click="addItem">添加工作经历</el-button>
       </el-form>
  </div>
</template>
<script>
export default {
  props:['items'],
  methods:{
    addItem(){
        const empty={}
        this.keys().map((key)=>{
            empty[key] = ''
        })
      this.items.push(empty)
    },
    removeItem(index){
      this.items.splice(index,1)
    }
  }
}
</script>
