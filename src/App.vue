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
    <!-- <table-slot-scope></table-slot-scope> -->

    <!-- collapse折叠模板懒加载 -->
    <collapse-lazy></collapse-lazy>

  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue';
import FormValidate from '@/components/FormValidate.vue';
import TransferSelf from '@/components/TransferSelf.vue';
import TableSlotScope from '@/components/TableSlotScope.vue';
import CollapseLazy from '@/components/CollapseLazy/index.vue';

export default {
  name: 'App',
  components: {
    HelloWorld, 
    FormValidate, 
    TransferSelf, 
    CollapseLazy
  }
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

.f-mgb20{
  margin-bottom: 20px;
}

.c-success{
  color: green;
}
.c-primay{
  color: blue
}
</style>
