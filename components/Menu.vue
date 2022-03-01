<template>
    <div id="menu">
        <div class="container-fluid">
            <div class="row">
                <div class="col-md-4 flex">
                    <div class="menu d-flex flex-row bd-highlight mb-3">
                        <div class="p-3 bd-highlight"><a href="/">HOME</a></div>
                        <div class="p-3 bd-highlight"><a href="/product">SHOP</a></div>
                        <div class="p-3 bd-highlight"><a href="/post">BLOG</a></div>
                        <div class="p-3 bd-highlight"><a href="/contact">CONTACT</a></div>
                    </div>
                </div>
                <div class="col-md-4 d-flex justify-content-center">
                    <svg viewBox="0 0 200 50">
                        <symbol id="s-text">
                            <text text-anchor="middle" x="50%" y="50%"> Cường - Shoes</text>
                        </symbol>

                        <g class = "g-ants">
                            <use xlink:href="#s-text" class="text-copy"></use>
                            <use xlink:href="#s-text" class="text-copy"></use>
                            <use xlink:href="#s-text" class="text-copy"></use>
                            <use xlink:href="#s-text" class="text-copy"></use>
                            <use xlink:href="#s-text" class="text-copy"></use>
                        </g>
                    </svg>
                </div>
                <div class="col-md-4 d-flex justify-content-end">
                    <div class="menu d-flex flex-row bd-highlight mb-3">
                        <div class="p-3 search__container">
                            <input class="search__input" type="text" placeholder="Search">
                        </div>
                        <div class="p-3 bd-highlight"><a href="/login">SIGN IN</a></div>
                       <!-- <div class="p-3 bd-highlight"><a href="/register">SIGN UP</a></div> -->
                        <div class="p-3 bd-highlight"><a href="/cart">CART</a> 
                            <span class="item-total">
                                {{itemCount}}
                            </span>
                        </div>
                    </div>
                </div>
            </div>
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
        async getCartOnpageLoad() {
            const response = await axios.post('http://127.0.0.1:8000/api/cart');
            this.itemCount =response.data.items
        }
    },

    created() {
        this.getCartOnpageLoad();
    },
}
</script>

<style scoped>

svg {
    display: block;
    font-size: 25px;
    width: 300px;
    margin: 0 auto;
}

.menu a {
    padding-bottom: 10px;
    color: black;
    font-size: 15px;
    text-decoration: none;
    display: inline-block;
    position: relative;
}

.menu a::after {
    content: '';
    position: absolute;
    left: 0;
    display: inline-block;
    height: 1em;
    width: 100%;
    border-bottom: 1px solid;
    margin-top: 10px;
    opacity: 0;
    -webkit-transition: opacity 0.35s, -webkit-transform 0.35s;
    transition: opacity 0.35s, transform 0.35s;
    -webkit-transform: scale(0,1);
    transform: scale(0,1);    
    }

.menu a:hover::after {
    opacity: 1;
	-webkit-transform: scale(1);
	transform: scale(1);
}

.text-copy {
    fill: none;
    stroke: white;
    stroke-dasharray: 6% 25%;
    stroke-width: 1px;
    stroke-dashoffset: 0%;
    animation: stroke-offset 3.5s infinite linear;
}

.text-copy:nth-child(1){
	stroke: #4D163D;
	animation-delay: -1;
}

.text-copy:nth-child(2){
	stroke: #840037;
	animation-delay: -2s;
}

.text-copy:nth-child(3){
	stroke: #BD0034;
	animation-delay: -3s;
}

.text-copy:nth-child(4){
	stroke: #BD0034;
	animation-delay: -4s;
}

.text-copy:nth-child(5){
	stroke: #FDB731;
	animation-delay: -5s;
}

@keyframes stroke-offset{
	100% {stroke-dashoffset: -35%;}
}

.search__input {
    border-radius: 20px;
}

.item-total {
    background-color: red;
    color: white;
    width: 50px;
    height: 50px;
    border-radius: 2px;
}

</style>