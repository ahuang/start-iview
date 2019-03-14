<template>
    <div>
        <h1>自带的transfer</h1>
        <p style="margin-bottom: 20px">只能通过中间的按钮对内容进行左右移动</p>
        <Transfer filterable :data="sourceData" :target-keys="targetKeys"  
            @on-change="handleMove" 
            :render-format="renderContent" :list-style="listStyle"></Transfer>
        <hr style="margin: 30px">
        <h1>改良后的transfer</h1>
        <p style="margin-bottom: 20px">点击内容即可实现左右移动</p>
        <TransferBetter filterable :data="sourceData" :target-keys="targetKeys"  
            @on-change="handleMove" @on-click-change="handleClickChange"
            :render-format="renderContent" :list-style="listStyle"></TransferBetter>        
    </div>
</template>
<script>
export default {
    name: 'TransferSelf',
        data () {
            return {
                sourceData: [
                    {key: '1', label: `item1${Math.random().toString(36).substr(2)}`, disabled: false, description: `The desc of item1`},
                    {key: '2', label: `item2${Math.random().toString(36).substr(2)}`, disabled: false, description: `The desc of item2`},
                    {key: '3', label: `item3${Math.random().toString(36).substr(2)}`, disabled: false, description: `The desc of item3`},
                    {key: '4', label: `item4${Math.random().toString(36).substr(2)}`, disabled: false, description: `The desc of item4`},
                    {key: '5', label: `item5${Math.random().toString(36).substr(2)}`, disabled: false, description: `The desc of item5`},
                    {key: '6', label: `item6${Math.random().toString(36).substr(2)}`, disabled: false, description: `The desc of item6`}
                ],
                targetKeys: ['2','5'],
                listStyle: { width: '200px', height: '300px'},
            }
        },
        methods: {
            renderContent (item) {
                return item.label;
            },
            // 自带的-点击中间按钮事件
            handleMove (newTargetKeys, direction, moveKeys) {
                console.log('handleMove....')
                this.targetKeys = newTargetKeys;
            },
            // 改良-点击左右列表项事件
            handleClickChange(selfType, itemKey){
                console.log('handleClickChange....');
                console.log(`selfType=${selfType}, itemKey=${itemKey}`);
                if(selfType === 'left'){
                    this.targetKeys = [...this.targetKeys, itemKey];
                }else{
                    this.targetKeys = this.targetKeys.filter(d => d !== itemKey);
                }

            }
        }    
}
</script>
<style>
.ivu-transfer-list-header{
    text-align: left;
}
.ivu-transfer-list-body-with-search .ivu-transfer-list-content{
    text-align: left;
}
</style>


