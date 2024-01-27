<script>
import Header from '../components/Header.vue';
import Slider from '../components/Slider.vue';
import Product from '../components/Product.vue'

export default {
    data() {
        return {


        }
    },

    components: {

        Header,
        Slider,
        Product,
    },



    watch: {



    },
    methods: {


    },
}
</script>




<template>
    <main>

        <section class="w-full max-h-screen flex flex-col">

            <!-- ////////////////////////////header//////////////////////////// -->
            <Header class="w-full"></Header>

            <div class="w-full flex justify-center items-center gap-x-40 flex-col lg:flex-row gap-y-7 lg:gap-y-0 lg:!mt-40">
                <!-- /////////////////////////////slider///////////////////////////////// -->
                <div class="w-full  lg:w-1/4">
                    <Slider></Slider>
                </div>
                <!-- ////////////////////////////////////////////////////prouduct////////////////////// -->
                <div class="w-full lg:w-1/4 flex justify-center items-center lg:items-start flex-col ">
                  <Product class="!gap-y-1 flex flex-col justify-center !mx-4"></Product>
                </div>
            </div>
        </section>
    </main>
</template>





<style scoped>
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}

input[type="number"] {
    -moz-appearance: textfield;
}
</style>
