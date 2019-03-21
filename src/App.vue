<template>
  <div id="app">
    <!-- vue-root -->
    <!-- <router-view/> -->

    <!-- hello-world -->
    <!-- <hello-world></hello-world>  -->
    
    <!-- iview form 表单验证 -->
    <!-- <form-validate></form-validate> -->


    <!-- 改良版本的transfer -->
    <!-- <transfer-self></transfer-self> -->

    <!-- table支持vue slot-scope语法的例子 -->
    <table-slot-scope></table-slot-scope>

  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld'
import FormValidate from '@/components/FormValidate'
import TransferSelf from '@/components/TransferSelf'
import TableSlotScope from '@/components/TableSlotScope'

export default {
  name: 'App',
  components: {HelloWorld, FormValidate, TransferSelf, TableSlotScope}
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
  margin-bottom: 360px;
}
</style>
