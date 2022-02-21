<template>
    <div>
         <Menu />
         <div class="register container pt-5 pb-5 mt-5 mb-5">
            <div class="row">
                <div class="register-left col-md-5">
                    <img src="../assets/images/background/bg-login.png">
                </div>
                <div class="register-right col-md-7 ">
                <h1 v-for="(item, key) in user" :key="key">{{item.name}}</h1>
                    <form   class="pl-4 pr-2 border-left">
                        <h5 class="mb-5">ĐĂNG NHẬP</h5>
                        <div class="mb-3">
                            <label for="exampleInputEmail1" class="form-label">Email</label>
                            <input v-model="login.email" type="email" class="form-control">
                        </div>
                        <div class="mb-3">
                            <label for="exampleInputPassword1" class="form-label">Mật khẩu</label>
                            <input v-model="login.password"  type="password" class="form-control" >
                        </div>
                        <!-- <div class="mb-3 form-check">
                            <input type="checkbox" class="form-check-input" >
                            <label class="form-check-label" for="exampleCheck1">Ghi nhớ mật khẩu</label>
                        </div> -->
                        <button @click.prevent="loginUser" type="submit" class="btn btn-primary" >Đăng Nhập</button>
                    </form>
                </div>
            </div>
        </div>
        <Footer />
    </div>
</template>
<script>
import Menu from '../components/Menu.vue'
import Footer from '../components/Footer.vue'
export default {
     components: { Menu, Footer },
    data() {
        return {
            login: {
                email: '',
                password: ''
            },
            user : []
            
        }
    },

    methods: {
        async loginUser() {
           this.user = await this.$axios.$post('http://127.0.0.1:8000/api/auth/login', this.login)
           return this.user
            // return this.$router.push('/')
        }
    },
}
</script>

<style scoped>
.register {
    margin-top: 20px;
    padding: 20px;
    box-shadow: rgba(50, 50, 93, 0.25) 0 6px 12px -2px, rgba(0, 0, 0, 0.3) 0 3px 7px -3px;
}
.register img {
    width: 100%;
}
</style>