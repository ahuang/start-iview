<template>
    <div>
        <ul class="m-wrap">
            <li v-for="item in numbers" :key="item">
                {{item}}
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    components: {},
    props:{
        value: Number
    },
    data () {
        return {
            numbers: Array.from(Array(this.value).keys())
        }
    },
    created () {
    },
    methods: {
    }
}
</script>
<style scoped>
.m-wrap{
    list-style: none;
    max-height: 200px;
    overflow: auto;
}    
</style>
