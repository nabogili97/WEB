<template>
    <div class="cart container-fulid mb-5">
        <div class="row">
            <div class="col-md-12">
                <div class="banner text-center d-flex align-items-center justify-content-center mb-5">
                    <h3>GIỎ HÀNG</h3>
                </div>
            </div>
            <div class="col-md-1"></div>
            <div class="col-md-7 ">
                <h4 class="p-3">Chi tiết giỏ hàng</h4>
                <b>Danh sacch test</b>{{itemCount}}
                <table class="table product-list text-center">
                    <thead>
                        <tr>
                            <th scope="col">STT</th>
                            <th scope="col">Sản phẩm</th>
                            <th scope="col">Size</th>
                            <th scope="col">Số lượng</th>
                            <th scope="col">Giá</th>
                            <th scope="col">Tổng tiền</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <th scope="row">1</th>
                            <td>
                                <div class="d-flex justify-content-lg-start ">
                                    <div class="img">
                                        <img src="https://xcimg.szwego.com/20210711/i1626015006_1835_0.jpg">
                                    </div>
                                    <div class="product-name pl-2">
                                        <span>Travis Scott x Air Jordan 6 </span>
                                    </div>
                                </div>
                            </td>
                            <td>
                                <span>40</span>
                            </td>
                            <td>
                                <div class="d-flex justify-content-lg-start product-qty ">
                                    <div class="d-flex justify-content-center">
                                        <input class="form-control" type="number" value="2">
                                    </div>
                                </div>
                            </td>
                            <td>
                                7.000.000 VNĐ 
                            </td>
                            <td>
                                14.000.000 VNĐ
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <div class="col-md-3 border bill">
                <h4 class="p-3 text-center border-bottom">HÓA ĐƠN</h4>
                <div class="d-flex justify-content-between pb-2">
                    <div>
                        <b>Số sản phẩm</b>
                    </div>
                    <div>
                       <b> Thành Tiền</b>
                    </div>
                </div>
                <div class="d-flex justify-content-between">
                    <div>
                        <span>2 sản phẩm</span>
                    </div>
                    <div>
                        14.000.000
                    </div>
                </div>
                <!-- <div class=" border-bottom mt-3 pb-3">
                    <b>Mã giảm giá:</b>
                    <div>
                        <input class="form-control">
                    </div>
                    <div>
                        <button type="button" class="btn btn-danger mt-1">Áp dụng</button>
                    </div>
                </div> -->
                <div class="d-flex justify-content-between pb-5 mt-5 border-top">
                    <div>
                        <b>Tổng tiền: </b>
                    </div>
                    <div>
                       <b> 14.000.000 VNĐ</b>
                    </div>
                </div>
                <div class="d-flex justify-content-center mb-3">
                    <button  class="btn btn-primary" >ĐẶT HÀNG</button>
                </div>
            </div>
            <div class="col-md-1"></div>
        </div>
    </div>
</template>
<script>
import axios from 'axios';
export default {
    setup() {
        
    },
    data() {
        return {
            itemCount: ''
        }
    },

    mounted() {
        this.$root.$on('changeInCart', (item) => {
            this.itemCount = item;
        })
    },

    methods: {
        async getCartitem() {
            const response = await axios.get('http://127.0.0.1:8000/api/checkout/get/items');

            console.log(response)


        }
    },

    created() {
        this.getCartitem();
    },
}
</script>
<style scoped>
.banner {
    height: 150px;
    background-color: #d9d9d9;
}

.product-list img {
    width: 80px;
    height: auto;
    object-fit: cover;
}

.product-qty  input{
    width: 30%;
}

.bill {
    background-color: #fafafa;
}
</style>