<template>
  <div id="app">
    <!-- vue-root -->
    <!-- <router-view/> -->

    <!-- hello-world -->
    <!-- <hello-world></hello-world>  -->
    
    <!-- iview form 表单验证 -->
    <form-validate></form-validate>

  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld'
import FormValidate from '@/components/FormValidate'

export default {
  name: 'App',
  components: {HelloWorld, FormValidate}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
