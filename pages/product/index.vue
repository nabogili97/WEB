<template>
    <div class="">
        <Menu />
        <Shop />
        <Footer />
    </div>
</template>
<script>
import Shop from '../../components/Shop.vue'
import Menu from '../../components/Menu.vue'
import Footer from '../../components/Footer.vue'
export default {
    components: { Menu, Shop, Footer },
    
       
}
</script>