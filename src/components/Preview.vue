<template>
  <div id="preview">
    <section>
      <h1>{{resume.profile.name || '请填写姓名'}}</h1>
      <p>{{resume.profile.city || '请填写城市'}} | {{resume.profile.birth || '请填写出生日期'}}</p>
      <hr>
    </section>
  <br>
   <section v-if="filter(resume.workHistory).length>0" >
     <h2>工作经历</h2>
     <ul>
       <li v-for="project in filter(resume.workHistory)" >
         <br>
        <h4>{{project.company || '请填写工作单位'}} </h4> | <p><i> {{project.time || '请填写工作时间'}}</i></p>
         <div>{{project.content || '请填写工作内容'}}</div>
        
         
       </li>
     </ul>
     <br>
     <hr>
   </section>
   <section v-if="filter(resume.projectHistory).length>0">
     <h2>项目经验</h2>
     <ul>
       <li v-for="project in filter(resume.projectHistory)" >
         <br>
        <h4>{{project.title || '请填写项目名称'}} </h4> 
         <div>{{project.content || '请填写项目简介'}}</div>
         
       </li>
     </ul>
     <br>
     <hr>
   </section>
   <section v-if="filter(resume.stydyHistory).length>0" >
     <h2>学习经历</h2>
     <ul>
       <li v-for="project in filter(resume.stydyHistory)" >
         <br>
        <h4>{{project.school || '请填写学校'}} </h4> | <p><i> {{project.duration || '请填写时间'}}</i></p>
         <div>{{project.major || '请填写专业'}}</div>
        
         
       </li>
     </ul>
     <br>
   
   </section>
   <section class="contact" >
    <hr>
    <br>
        <p>{{resume.contact.cellphone || '请填写电话'}}</p> |
        <p>{{resume.contact.email || '请填写邮箱地址'}} | {{resume.contact.wechat || '请填写微信号'}}</p>
   
    </section>
  </div>
</template>

<script>
export default {
  props:['resume'],
  methods:{
    filter(arr){//导出非空对象
      return arr.filter(item=>!this.isEmpty(item))
    },
    isEmpty(obj){//只要有一个value不是falsy，就返回false
      let empty = true
      for(let key in obj){
        if(obj[key]){
          empty = false
          break
        }
        return empty
        
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
#preview{
  min-height:100px;
  padding: 16px 32px;
  section{
    padding:16px 0;
    h4,p{
      display: inline;
    }
  }


}
</style>
