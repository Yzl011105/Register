<template>
    <div>
        <div class="title-cantainer">
            <h3>登录系统</h3>
        </div>
        <el-form
            :model="loginForm"
            status-icon
            :rules="loginRules"
            ref="loginForm"
            label-width="100px"
            class="login-form"
        >
            <el-form-item
                label="电话号"
                prop="phone"
            >
                <el-input
                    v-model="loginForm.phone"
                    autocomplete="off"
                ></el-input>
            </el-form-item>
            <el-form-item
                type="password"
                label="密码"
                prop="password"
            >
                <el-input
                    type="password"
                    v-model="loginForm.password"
                    autocomplete="off"
                ></el-input>
            </el-form-item>
        </el-form>
    </div>
</template>

<script>

export default {
    name: "Register",
    components: {
    },
    data() {
        const validatePassword = (rule, value, callback) => {
            if (value.length < 6) {
                callback(new Error('请输入最少六位密码'))
            } else {
                callback()
            }
        }
        return {
            loginForm: {
                phone: '',
                password: ''
            },
            loginRules: {
                password: [{ required: true, trigger: 'blur', validator: validatePassword }]
            }
        }
    }
};
</script>
