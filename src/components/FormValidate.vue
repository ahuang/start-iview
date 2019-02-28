<template>
    <div style="width: 30vw; margin: 0 auto">
        <h1>iview form validate 表单验证 </h1>
        <Form ref="formValidate" :model="formValidate" :rules="ruleValidate" :label-width="80">
            <FormItem label="姓名" prop="name"><Input v-model="formValidate.name" placeholder="请输入姓名"></Input></FormItem>
            <FormItem label="邮件" prop="mail"><Input v-model="formValidate.mail" placeholder="请输入邮件"></Input></FormItem>
            <FormItem label="城市" prop="city">
                <Select v-model="formValidate.city" placeholder="请选择城市">
                    <Option value="beijing">北京</Option>
                    <Option value="shanghai">上海</Option>
                    <Option value="shenzhen">深圳</Option>
                </Select>
            </FormItem>
            <FormItem label="性别" prop="gender">
                <RadioGroup v-model="formValidate.gender">
                    <Radio label="male">男</Radio>
                    <Radio label="female">女</Radio>
                </RadioGroup>
            </FormItem>
            <FormItem label="兴趣爱好" prop="interest">
                <CheckboxGroup v-model="formValidate.interest">
                    <Checkbox value="eat" label="吃"></Checkbox>
                    <Checkbox value="sleep" label="睡"></Checkbox>
                    <Checkbox value="run" label="跑"></Checkbox>
                </CheckboxGroup>
            </FormItem>
            <FormItem>
                <Button type="primary" @click="handleSubmit('formValidate')">Submit</Button>
                <Button @click="handleReset('formValidate')" style="margin-left: 8px">Reset</Button>
            </FormItem>
        </Form>    
    </div>
</template>
<script>
    export default {
        name: 'FormValidate',
        data () {
            const validateName = (rule, value, callback) => {
                console.log(value, value === '')
                if(value === ''){
                    callback(new Error('自定义校验-名称不能为空'));
                }else{
                    callback();
                }
            };
            return {
                // 表单数据和v-model绑定
                formValidate: {
                    name: '',
                    mail: '',
                    city: '',
                    gender: '',
                    interest: [],
                },
                // 校验规则和prop绑定
                ruleValidate: {
                    name: [{ validator: validateName, required: true, trigger: 'blur' }],
                    mail: [{ required: true, message: '非空校验-邮件', trigger: 'blur' },
                        { type: 'email', message: '格式校验-邮件', trigger: 'blur' }],
                    city: [{ required: true, message: '非空校验-城市', trigger: 'change' }],
                    gender: [{ required: true, message: '非空校验-性别', trigger: 'change' }],
                    interest: [{ required: true, type: 'array', min: 1, message: '非空校验-兴趣爱好', trigger: 'change' },
                        { type: 'array', max: 2, message: '数量校验-最多选择2个-兴趣爱好', trigger: 'change' }
                    ]
                }
            }
        },
        methods: {
            handleSubmit (name) {
                // 提交之前先校验表单   
                this.$refs[name].validate((valid) => {
                    if (valid) {
                        this.$Message.success('Success!');
                        // 参数使用深拷贝
                        let params = {...this.formValidate}
                        console.log(params);                        
                    } else {
                        this.$Message.error('Fail!');
                    }
                })
            },
            // reset操作会清空表单数据，主要要在异步请求结束之后调用
            handleReset (name) {
                this.$refs[name].resetFields();
            }
        }
    }
</script>
