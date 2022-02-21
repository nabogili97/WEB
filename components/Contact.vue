<template>
    <div class="contact container-fluid">
        <div class="row">
            <div class="bg-contact col-md-12">
                <img src="../assets/images/slide1.png">
            </div>
            <div class="col-md-12 mt-5">
                <h3 class=" text-center">CONTACT</h3>
            </div>
            <div class="container mt-5 mb-5 contact-cards">
                <div class="row">
                    <div class="col-md-5 p-0">
                        <div class="contact-card">
                            <h4 class="mb-5">Contact</h4>
                            <div class="mail mb-5">
                                <b>BY MAIL</b>
                                <p>Ngocuong691@gmail.com</p>
                            </div>
                            <div class="social  mb-5">
                                <b>Social</b>
                                <div class="d-flex justify-content-start">
                                    <div class="pr-3">Zalo  </div>
                                    <div class="pr-3">Youtube  </div>
                                    <div>Facebook</div>
                                </div>
                            </div>
                            <div class="description mb-5 pl">
                                <b>BY FORM</b>
                                <p>sadsa asd asd as ddas dsad sad asd asd sad asd asd sadas as dad </p>
                            </div>
                            <div class="address">
                                <b>Địa chỉ:</b>
                                <p>Tổ 5, Quang Minh, Mê Linh, Hà Nội</p>
                            </div>
                        </div>
                    </div>
            <div class="col-md-7 mt-5 ">
                <form class="pl-3 pr-3 pb-3">
                    <div class="form-group">
                        <label for="formGroupExampleInput">Your Name</label>
                        <input type="text" class="form-control" id="formGroupExampleInput" placeholder="Example input">
                    </div>
                    <div class="form-group">
                        <label for="exampleInputEmail1">Email </label>
                        <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Enter email">
                    </div>
                    <div class="form-group">
                        <label for="formGroupExampleInput">Content </label>
                        <textarea class="form-control box-text" />
                    </div>
                    <button type="submit" class="btn btn-primary">Send</button>
                </form>
            </div>
                </div>
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
.contact img {
    max-height: 250px;
    width: 100%;
    object-fit:cover;
}

.contact-cards {
    box-shadow: rgba(0, 0, 0, 0.24) 0 3px 8px;
}

.contact-card {
    background-color: #f0eee3;
    opacity: 0.5;
    padding: 30px;

}

.box-text {
    height: 180px;
}
</style>