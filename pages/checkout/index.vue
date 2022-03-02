<template>
    <div>
        <Menu />
        <Checkout />
        <Footer />
    </div>
</template>
<script>
import Checkout from '../../components/Checkout.vue'
import Footer from '../../components/Footer.vue'
import Menu from '../../components/Menu.vue'
export default {
  components: { Checkout, Menu, Footer },
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
