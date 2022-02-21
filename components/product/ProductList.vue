<template>
    <div class="product-list container">
        <div class="row d-flex justify-content-between">
            <div v-for="(item, index) in products" :key="index" class="product-card col-md-3 col-sm-6 col-6 card-group mb-4">
                <div class="card" >
                    <img class="card-img-top" :src=item.image alt="Card image cap">
                    <div class="card-body">
                        <h5 class="card-title product-name"> 
                            <NuxtLink :to="'/product/' + item.id" style="text-decoration:none">
                                {{item.name}}
                            </NuxtLink>
                        </h5>
                        <p class="card-text product-price">{{formatPrice(item.retail_price)}} VNĐ </p>
                       
                        <a href="#" class="btn btn-primary cart-add">THÊM GIỎ HÀNG</a>
                    </div>
                </div>
            </div>
        </div>
        <!-- <div class="row">
            <div class="col-md-8">
                <nav>
                    <ul  v-for="(page, key) in pagination.meta" :key="key" >
                        <li><a href="" @click="view">{{page}}</a></li>
                    </ul>
                </nav>
            </div>
            <div class="col-md-4">
                Page: {{pagination.meta.from}} - {{pagination.meta.to}}
                Total: {{pagination.meta.total}}
            </div>
        </div> -->
    </div>
</template>

<script>
import { fas } from '@fortawesome/free-solid-svg-icons'
export default {
    props: ['products'],
    computed: {
        fas () {
            return fas 
        },
      },
    data() {
        return {
            pagination: {}
        }
    },
    // created() {
    //     this.viewProduct();
    // },
    async fetch() {
      this.pagination = await fetch("http://127.0.0.1:8000/api/product/listProduct").then(res => res.json());
      return this.pagination
    },
    methods: {
        // viewProduct(pagi){
        //     pagi = pagi || '/api/product/listProduct';
        //     fetch(pagi)
        //     .then(res => res.json())
        //     .then(res => {
        //         this.product = res.data;
        //         this.pagination = {
        //             current_page: res.meta.current_page,
        //             last_page: res.meta.last_page,
        //             from_page: res.meta.from,
        //             to_page: res.meta.to,
        //             total_page: res.meta.total,
        //             path_page: res.meta.path+"?page=",
        //             first_link: res.link.first,
        //             last_link: res.link.last,
        //             prev_link: res.link.prev,
        //             next_link: res.link.next
        //         };
        //     }).catch(err => console.log(err));
        // },
        formatPrice(value) {
            const val = (value/1).toFixed(0).replace('.', ',')
            return val.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ".")
        }
    }
}
</script>
<style scoped>
.card {
    width: 90%;
}

.product-price {
    color: red;
}

@media (max-width: 575.98px)  {
   .product-card{
       padding-right: 0 !important;
       padding-left: 0 !important;
   }

    h5 {
        font-size: 17px;
    }

    .product-price {
        font-size: 12px;
    }

    .product-name {
        font-size: 16px;
    }

    .cart-add {
        height: 30px;
    }

    a {
        font-size: 10px;
    }
}
 .product-name a {
    color: black;
}

@media (max-width: 1199.98px) {
    .product-card {
        padding-left: 20px;
        padding-right: 20px;
    }
}

.size-value {
    border: 0.5px solid black;
    border-radius: 2px;
}

.product-name {
    min-height: 50px;
}

.card-img-top {
    min-height: 187px;
    max-height: 187px;
    object-fit: cover;
}
</style>