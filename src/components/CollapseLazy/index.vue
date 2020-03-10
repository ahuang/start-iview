<template>
    <div>
        <h1>折叠面板的懒加载</h1>
        <h3 class="f-mgb20 c-success">
            默认：所有面板折叠起来，内容不加载<br>
            点击：加载面板内部组件<br>
            面的例子用注释代码的方式对比效果<br>
        </h3>
        <h3  class="f-mgb20">没有懒加载的例子</h3>
        <without-lazy :listOrigin="listOrigin"></without-lazy>
        
        <h3  class="f-mgb20">有懒加载的例子</h3>
        <!-- <with-lazy :listOrigin="listOrigin"></with-lazy> -->
    </div>
</template>
<script>
import withoutLazy from "@/components/CollapseLazy/withoutLazy.vue";
import withLazy from "@/components/CollapseLazy/withLazy.vue";

export default {
    components: {
        withoutLazy,
        withLazy
    },
    data () {
        return {
            listOrigin: [20000, 9000]
        }
    },
    created () {
    },
    methods: {
    }
}
</script>
<style scoped>
    
</style>
