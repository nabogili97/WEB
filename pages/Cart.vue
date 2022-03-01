<template>
    <div>
        <Menu />
        <Cart />
        <Footer />
    </div>
</template>
<script>
import Cart from '../components/Cart.vue'
import Footer from '../components/Footer.vue'
import Menu from '../components/Menu.vue'
export default {
  components: { Cart, Menu, Footer },
    setup() {
        
    },
    data() {
        return{
            
        }

    },
    methods: {
        getCartItems() {

        }
    },
    created() {
        this.getCartItems()
    },
}
</script>
