<template>
  <div id="topbar">
   <div class="logo">
     VueResumer
   </div>
   <div class="actions">
     <button>register</button>
     <button>login</button>
   </div>
  </div>
</template>

<script>
export default {
  name: 'Topbar',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
#topbar{
  // border:1px solid green;
  min-height:100px;
  display:flex;
  justify-content: space-between;
  padding: 16px;
}
</style>
