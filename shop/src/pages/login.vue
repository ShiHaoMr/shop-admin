<template>
    <div class="flex min-h-screen">
        <el-col :lg="16" :md="12"
            class="min-h-screen  bg-indigo-500 flex justify-center items-center text-light-50 text-xl font-semibold">

            欢迎光临

        </el-col>
        <el-col :lg="8" :md="12" class="flex flex-col justify-center items-center">
            <h3 class="text-2xl text-3xl font-extrabold">欢迎回来</h3>
            <div class="my-5 text-gray-200"> ——— &emsp;账号密码登录&emsp; ———</div>
            <el-form :model="form" ref="ruleFormRef" :rules="rules" class="w-[250px]">
                <el-form-item prop="username">
                    <el-input v-model="form.username" placeholder="请填写用户名">
                        <template #prefix>
                            <el-icon class="el-input__icon">
                                <User />
                            </el-icon>
                        </template>
                    </el-input>
                </el-form-item>
                <el-form-item prop="password">
                    <el-input v-model="form.password" placeholder="请填写密码">
                        <template #prefix>
                            <el-icon class="el-input__icon">
                                <Lock />
                            </el-icon>
                        </template>
                    </el-input>
                </el-form-item>
                <el-form-item>
                    <el-button class="w-[250px]" type="primary" round color="#626aef" @click="onSubmit">登 录</el-button>
                </el-form-item>
            </el-form>

        </el-col>
    </div>
</template>

<script setup>
import { reactive, ref } from 'vue'

const formSize = ref('default')
const ruleFormRef = ref()
// do not use same name with ref
const form = reactive({
    username: '',
    password: '',
})
const rules = reactive({
    username: [
        { required: true, message: '请填写用户名', trigger: 'blur' },
    ],
    password: [
        { required: true, message: '请填写密码', trigger: 'blur' },
    ],
})

const submitForm = async(FormInstance | undefined) => {
    if (!formEl) return
    await formEl.value.validate((valid, fields) => {
        if (valid) {
            console.log('submit!')
        } else {
            console.log('error submit!', fields)
        }
    })
}



const onSubmit = () => {
    console.log('submit!')
}
</script>
<style></style>