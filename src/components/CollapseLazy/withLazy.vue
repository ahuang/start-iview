<template>
    <div>
        <Collapse v-model="related" style="margin: 0 200px">
            <Panel v-for="item in list" :name="item.label" :key="item.value">
                循环{{item.label}}次
                <p slot="content" v-if="related.includes(item.label)">
                    <number-list v-model="item.value"></number-list>
                </p>
            </Panel>
        </Collapse>        
    </div>
</template>
<script>
import numberList from "@/components/CollapseLazy/numberList.vue";

export default {
    props:{
        listOrigin: Array
    },
    components: {
        numberList
    },
    data () {
        return {
            list: [],
            related: []            
        }
    },
    created () {
        this.list = this.listOrigin.map(d=>{
            return {
                label: d + '',
                value: d
            }
        });
    },
    methods: {
    }
}
</script>
<style scoped>
    
</style>
