<template>
<!-- import { setTimeout } from 'timers'; -->
  <div id="editor">
   <nav>
     <ol>
       <li v-for="i in [0,1,2,3,4]"
       v-bind:class="{active:currentTab === i}"
       v-on:click="currentTab = i">
            <svg class="icon" >
            <use v-bind:xlink:href=" `#icon-${icons[i]}` "></use>
        </svg></li>
     
     </ol>
   </nav>
   <ol class="panes">
     <li v-bind:class="{active:currentTab === 0}">
      <Profile v-bind:profile="resume.profile"/>
     </li>
     <li v-bind:class="{active:currentTab === 1}">
    
       <ItemsEditor v-bind:items="resume.workHistory" 
         v-bind:title="'工作经历'"
        v-bind:labels="{company:'单位',content:'工作内容',time:'时间'}"/>
     </li>
     <li v-bind:class="{active:currentTab === 2}">
      
       <ItemsEditor v-bind:items="resume.stydyHistory" 
         v-bind:title="'学习经历'"
        v-bind:labels="{school:'学校', duration:'时间', major:'专业'}"/>

     </li>
     <li v-bind:class="{active:currentTab === 3}">
      <ItemsEditor v-bind:items="resume.projectHistory" 
      title="项目经历"
        v-bind:labels="{title:'项目名称',content:'项目简介'}"/>
     </li>
     <li v-bind:class="{active:currentTab === 4}">
        <Contact v-bind:contact="resume.contact"/>
     </li>


   </ol>
  </div>
</template>

<script>
import Profile from './Profile'
import ItemsEditor from './ItemsEditor'
import Contact from './Contact'
export default {
  components:{
    Profile,
    ItemsEditor,
    Contact,
  },
  props:['resume'],
  data(){
    return{
      currentTab:0,
      icons:[ 
        'shenfen','work0','iceducation','xiangmu','phone'
      ],
      
    }
  },
  methods:{

  },

  //组件创建之后的回调
  created(){
    console.log(this.profile)
    setTimeout(()=>{console.log(this.profile)},10000)
  }
}
</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
#editor{
  min-height:100px;
  display: flex;
  nav{
    background:#3F8BFA;
    width: 80px;
    ol{      
      li{
        padding: 16px 0;
        text-align: center;
        .icon {
          width:24px;
          height:24px;
          fill:white;
        }
        &.active{
          background: white;
          .icon{
          fill:#3F8BFA;
          }
        }
      }
    }
  };
  .panes{
    flex:1;
    .container{
      position: relative;
      .el-icon-circle-close{
        position: absolute;
        right:0;
        top:0;
      };
    }
    >li{
      display: none;
      padding:32px;
      overflow: auto;
      height:100%;
      &.active{
        display: block;
      }
    }
  }

}
</style>
