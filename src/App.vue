<template>
  <div id="app" v-bind:class="{previewMode:previewMode}">
    <Topbar  class="topbar" v-on:preview="preview"/>
    <main>
      <Editor class="preview" v-bind:resume="resume"/>
      <Preview class="preview" v-bind:resume="resume"/>
    </main>
    <el-button id="exit-preview"v-on:click="exitPreview">退出预览</el-button>
  </div>
</template>

<script>
import Topbar from './components/Topbar'
import Preview from './components/Preview'
import Editor from './components/Editor'


export default {
  data(){
    return{
      previewMode:false,
      resume:{
        profile:{
                name:'',
                birth:'',
                city:'',
            },
            contact:{
                cellphone:'',
                email:'',
                wechat:'',
            },
            workHistory:[
              {company:'',content:'',time:''}
            ],
            stydyHistory:[
              {school:'',duration:'',major:''}
            ],
            projectHistory:[
              {title:'',content:''}
            ] 
      }
    }
  },
  name: 'App',
  components: {
    Topbar,
    Preview,
    Editor,
  },
  methods:{
    preview(){
      this.previewMode = true
    },
    exitPreview(){
       this.previewMode = false
    }
  },
  // created(){
  //   this.$on('preview',()=>{
  //     alert('preview')
  //   })
  // }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height:100vh;
  display: flex;
  flex-direction: column ;
  color:#333;
  

}
.icon {
       width: 1em; height: 1em;
       vertical-align: -0.15em;
       fill: currentColor;
       overflow: hidden;
}

.topbar{
  box-shadow: 0 0 3px hsla(0,0,0,.5);
  position: relative;
  z-index: 1;
  transition: all 5s ease;
  
}
main{
  background: #ddd;
  display: flex;
  flex:1;
  >.editor{
    width:30em;
    margin:16px 8px 16px 16px;
    background: white;
    box-shadow: 0 0 3px hsla(0,0,0,.5);
    border-radius: 2px;
    overflow:auto;

  }
  >.preview{
    flex:1;
    margin:16px 8px 16px 16px;
    background: white;
    box-shadow: 0 0 3px hsla(0,0,0,.5);
    border-radius: 2px;
    overflow:auto;
  }
}
.previewMode{
  #preview{
    max-width: 800px;
    margin-left:auto;
    margin-right:auto;
  }
  #topbar,#editor{
    display:none;
  }
  #exit-preview{
  display: block;
}
  
}
#exit-preview{
  display: none;
}
</style>
