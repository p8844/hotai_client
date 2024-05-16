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
                    <el-tabs type="border-card" :stretch="true">
                        <el-tab-pane label="登录">
                            <el-form class="loginForm" label-width="auto" :model="loginForm" style="max-width: 600px">
                                <el-form-item label="账 号">
                                    <el-input v-model="loginForm.account" placeholder="请输入账号" />
                                </el-form-item>
                                <el-form-item label="密 码">
                                    <el-input v-model="loginForm.password" placeholder="请输入密码" />
                                </el-form-item>
                                <el-form-item>
                                    <el-button type="primary" @click="" style="margin-left: 90px;">
                                        登录
                                    </el-button>
                                    <el-button @click="">注册</el-button>
                                </el-form-item>
                            </el-form>
                        </el-tab-pane>
                        <el-tab-pane label="注册">注册</el-tab-pane>
                    </el-tabs>
                </div>
            </el-main>
        </el-container>
    </div>
</template>
<script setup lang="ts">
import { ref } from 'vue'
const loginForm = ref({
    account: '',
    password: ''
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
.main .formContainer .loginForm {
    margin-top: 20px;
}
</style>
