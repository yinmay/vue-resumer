<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <Topbar class="topbar"/>
    <main>
      <Editor class="editor"/>
      <Preview class="preview"/>
    </main>
  </div>
</template>

<script>
import Topbar from './components/Topbar'
import Preview from './components/Preview'
import Editor from './components/Editor'


export default {
  name: 'App',
  components: {
    Topbar,
    Preview,
    Editor,
   
  }
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

}
.topbar{
  // background: red
}
main{
  // background: green;
  display: flex;
  flex:1;
  >.editor{
    width:20em
  }
  >.preview{
    flex:1
  }
}
</style>
