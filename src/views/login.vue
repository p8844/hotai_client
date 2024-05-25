<template>
    <div class="common-layout">
        <el-container>
            <el-header class="header">
                <div class="headerContent">
                    <h3>后台管理系统</h3><span>欢迎</span>
                </div>
            </el-header>
            <el-main class="main">
                <div class="formContainer">
                    <el-tabs type="border-card" v-model="activeName" :stretch="true">
                        <el-tab-pane label="登录" name="first">
                            <el-form class="loginForm" label-width="auto" :model="loginForm" :rules="rules" style="max-width: 600px">
                                <el-form-item label="账 号" prop="account">
                                    <el-input v-model="loginForm.account" placeholder="请输入账号" />
                                </el-form-item>
                                <el-form-item label="密 码" prop="password">
                                    <el-input v-model="loginForm.password" placeholder="请输入密码" />
                                </el-form-item>
                                <el-form-item>
                                    <el-button type="primary" @click="" style="margin-left: 80px;">
                                        登录
                                    </el-button>
                                    <el-button @click="activeName = 'second'">注册</el-button>
                                </el-form-item>
                            </el-form>
                        </el-tab-pane>
                        <el-tab-pane label="注册" name="second">
                            <el-form class="registerForm" label-width="auto" :model="registerForm" :rules="rules" style="max-width: 600px">
                                <el-form-item label="账 号" prop="account">
                                    <el-input v-model="registerForm.account" placeholder="请输入账号" />
                                </el-form-item>
                                <el-form-item label="密 码" prop="password">
                                    <el-input v-model="registerForm.password" placeholder="请输入密码" />
                                </el-form-item>
                                <el-form-item>
                                    <el-button type="primary" style="margin-left: 80px;">注册</el-button>
                                    <el-button @click="activeName = 'first'">
                                        登录
                                    </el-button>
                                </el-form-item>
                            </el-form>
                        </el-tab-pane>
                    </el-tabs>
                </div>
            </el-main>
        </el-container>
    </div>
</template>
<script setup lang="ts">
import { ref } from 'vue'

const activeName = ref('first')

interface UserInfo {
    account: string
    password: string
}
const loginForm = ref<UserInfo>({
    account: '',
    password: ''
})
const registerForm = ref<UserInfo>({
    account: '',
    password: ''
})

const rules = ref({
    account: [
        {
            required: true,
            message: '请输入账号',
            trigger: 'blur'
        },
        {
            min: 5,
            max: 10,
            message: '账号长度在 5 到 10 个字符',
            trigger: 'blur'
        }
    ],
    password: [
        {
            required: true,
            message: '请输入密码',
            trigger: 'blur'
        },
        {
            min: 6,
            max: 12,
            message: '密码长度在 6 到 12 个字符',
            trigger: 'blur'
        }
    ]
})
</script>
<style scoped>
/*  头部样式 */
.header {
    background-color: #000000;
}

.header .headerContent {
    padding: 0 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    /* background-color: #000000; */
    color: #fff;
}

.headerContent h3 {
    margin: 0;
    padding: 0;
    font-size: 30px;
}

.main {
    position: relative;
    margin: 0;
    padding: 0c;
    height: calc(100vh - 60px);
    background-image: url(@/assets/image/login_bg.jpg);
    background-repeat: no-repeat;
    background-position: 0 0;
    background-size: cover;
}

.main .formContainer {
    height: 500px;
    width: 300px;
    border-radius: 10px;

    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.main .formContainer .loginForm,
.main .formContainer .registerForm {
    margin-top: 20px;
}
</style>
