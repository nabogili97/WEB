<template>
    <div class="blog">
        <Menu />
        <div class="col-md-12">
                <div class="banner text-center d-flex align-items-center justify-content-center mb-5">
                    <h3>BÀI VIẾT</h3>
                </div>
            </div>
        <Post />
        <Footer class="mt-5" />
    </div>
</template>
<script>
import Post from '../../components/Post.vue'
import Footer from '../../components/Footer.vue'
import Menu from '../../components/Menu.vue'
export default {
  components: { Post, Menu, Footer },
    data() {
        return {

        }
    }
}
</script>
<style scoped>
.banner {
    height: 100px;
    background-color: #d9d9d9;
}
</style>