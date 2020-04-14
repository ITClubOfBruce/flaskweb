<template id="hello">
  <h1>{{ msg }}</h1>
</template>

<script>
Vue.component("hello-component",{
  el:function(){
    return "#hello";
  },
  data:function(){
    return {
      msg:'hello'
    }
  }
})
new Vue({
  el:'#app',
  data:{
    item:'10'
  }
})
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
