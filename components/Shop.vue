<template>
    <div class="shop container-fluid">
        <div class="row">
            <div class="col-md-12">
                <div class="banner text-center d-flex align-items-center justify-content-center mb-5">
                    <h3>S H O P</h3>
                </div>
            </div>
            <div class="col-md-2 border-right">
                <MenuLeft />
            </div>
            <div class="col-md-10">
                <product-list :products="products" />
            </div>
        </div>
    </div>
</template>
<script>
import MenuLeft from './shop/MenuLeft.vue'
import ProductList from './product/ProductList.vue'
export default {
     components: {  ProductList, MenuLeft},
    data() {
        return {
        products: [],
        news: []
    }
  },
   async fetch() {
      this.products = await fetch("http://127.0.0.1:8000/api/productLists").then(res => res.json());
      return this.products 
    }, 
}
</script>
<style scoped>
.banner {
    height: 100px;
    background-color: #d9d9d9;
}

.title-card h2 {
    letter-spacing: 3px;
}

.title-border {
  height: 2px;
  width: 15%;
  background-color: black;
  margin: auto;
}
</style>