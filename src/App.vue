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
    overflow:hidden;




  }
}
</style>
