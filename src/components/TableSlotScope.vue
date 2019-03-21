<template>
    <div>
        <h1>table use slot-scope</h1>
        <Table :width="480" :columns="col" :data="list"  style="margin: 0 auto;">
            <template slot="rate" slot-scope="{row,index}">
                {{rateCN(row.score)}}
            </template>
        </Table>
    </div>
</template>
<script>
export default {
    name: 'TableSlotScope',
    data(){
        return {
            col: [
                {
                    key: 'id',
                    title: 'id'
                },
                {
                    key: 'name',
                    title: '名称'
                },
                {
                    key: 'score',
                    title: '分数'
                },
                {
                    key: 'rate',
                    title: '等级',
                    slot: 'rate'
                    // render: (h,{row,index})=>{
                    //     return h('div',{}, this.rateCN(row.score))
                    // }
                }
            ],
            list: [
                {id: 1, name: '张三', score: 83},
                {id: 1, name: '张三', score: 70},
                {id: 1, name: '张三', score: 91},
                {id: 1, name: '张三', score: 100},
                {id: 1, name: '张三', score: 55},
                {id: 1, name: '张三', score: 65},
            ]
        }
    },
    methods: {
        rateCN(score){
            if(score>=90){
                return '优秀'
            }else if(score >=70){
                return '良好'
            }else if(score >= 60){
                return '及格'
            }else {
                return '不及格'
            }

        }
    }
}
</script>

