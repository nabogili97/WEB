<template>
    <div class="register container pt-5 pb-5 mt-5 mb-5">
        <div class="row">
            <div class="register-left col-md-5">
                <img src="../assets/images/background/bg-log-up.png">
            </div>
            <div class="register-right col-md-7 ">
                <form class="pl-4 pr-2 border-left">
                    <h5 class="mb-5">ĐĂNG KÝ</h5>
                    <div class="mb-3">
                        <label for="exampleInputEmail1" class="form-label">Email</label>
                        <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
                    </div>
                    <div class="mb-3">
                        <label for="exampleInputPassword1" class="form-label">Mật khẩu</label>
                        <input type="password" class="form-control" id="exampleInputPassword1">
                    </div>
                    <div class="mb-3">
                        <label for="exampleInputPassword1" class="form-label">Xác nhận mật khẩu</label>
                        <input type="password" class="form-control" id="exampleInputPassword1">
                    </div>
                    <button type="submit" class="btn btn-primary">Đăng Ký</button>
                </form>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    setup() {
        
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