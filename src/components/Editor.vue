<template>
<!-- import { setTimeout } from 'timers'; -->
  <div id="editor">
   <nav>
     <ol>
       <li v-for="i in [0,1,2,3,4,5]"
       v-bind:class="{active:currentTab === i}"
       v-on:click="currentTab = i">
            <svg class="icon" >
            <use v-bind:xlink:href=" `#icon-${icons[i]}` "></use>
        </svg></li>
     
     </ol>
   </nav>
   <ol class="panes">
     <li v-bind:class="{active:currentTab === 0}">
      <Profile v-bind:profile="profile"/>
     </li>
     <li v-bind:class="{active:currentTab === 1}">
       <WorkHistory v-bind:workHistory="workHistory"/>
     </li>
     <li v-bind:class="{active:currentTab === 2}">
        <h2>学习经历</h2>
     </li>
     <li v-bind:class="{active:currentTab === 3}">
        <h2>项目经历</h2>
     </li>
     <li v-bind:class="{active:currentTab === 4}">
        <h2>联系方式</h2>
     </li>
     <li v-bind:class="{active:currentTab === 5}">
       <h2>获奖经历</h2>
     </li>

   </ol>
  </div>
</template>

<script>
import Profile from './Profile'
import WorkHistory from './WorkHistroy'
export default {
  components:{
    Profile,
    WorkHistory,
  },
  data(){
    return{
      currentTab:0,
      icons:[ 
        'shenfen','work0','iceducation','xiangmu','phone','icon--'
      ],
      profile:{
          name:'',
          birth:'',
          city:'',
      },
      workHistory:[
        {company:'',content:'',time:''}
      ]  
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
    background:#000;
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
          fill:black;
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
