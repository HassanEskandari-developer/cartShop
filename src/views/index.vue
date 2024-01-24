<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/free-mode';
import 'swiper/css/navigation';
import 'swiper/css/thumbs';

import { FreeMode, Navigation, Thumbs } from 'swiper/modules';
export default {
    data() {
        return {

            modules: [FreeMode, Navigation, Thumbs],
            thumbSwiper: null

        }
    },

    components: {
        Swiper,
        SwiperSlide,
    },



    watch: {



    },
    methods: {
        setThumbsSwiper(swiper) {
            this.thumbSwiper = swiper
        }

    },
}
</script>




<template>
    <main>

        <section class="w-full max-h-screen flex flex-col">

            <!-- ////////////////////////////header//////////////////////////// -->

            <header class="w-full h-20 border flex justify-center items-center">
                <div class="flex lg:hidden border border-blue-400 ">
                    <svg class="w-[40px] h-[40px]" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"
                        fill="currentColor">
                        <path
                            d="M8 4H21V6H8V4ZM4.5 6.5C3.67157 6.5 3 5.82843 3 5C3 4.17157 3.67157 3.5 4.5 3.5C5.32843 3.5 6 4.17157 6 5C6 5.82843 5.32843 6.5 4.5 6.5ZM4.5 13.5C3.67157 13.5 3 12.8284 3 12C3 11.1716 3.67157 10.5 4.5 10.5C5.32843 10.5 6 11.1716 6 12C6 12.8284 5.32843 13.5 4.5 13.5ZM4.5 20.4C3.67157 20.4 3 19.7284 3 18.9C3 18.0716 3.67157 17.4 4.5 17.4C5.32843 17.4 6 18.0716 6 18.9C6 19.7284 5.32843 20.4 4.5 20.4ZM8 11H21V13H8V11ZM8 18H21V20H8V18Z">
                        </path>
                    </svg>
                </div>

                <div class="lg:w-1/4 text-end">
                    <h1 class="font-bold lg:!px-10">
                        sneaker
                    </h1>
                </div>

                <nav class="hidden lg:flex lg:w-2/4 ">
                    <ul class="flex gap-7">
                        <li>Collection</li>
                        <li>Men</li>
                        <li>Women</li>
                        <li>About</li>
                        <li>Contanct</li>
                    </ul>
                </nav>

                <div class="flex  lg:w-1/4 h-full justify-center items-center lg:gap-x-7">
                    <svg class="w-[30px] h-[25px]" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"
                        fill="currentColor">
                        <path
                            d="M4.00436 6.41686L0.761719 3.17422L2.17593 1.76001L5.41857 5.00265H20.6603C21.2126 5.00265 21.6603 5.45037 21.6603 6.00265C21.6603 6.09997 21.6461 6.19678 21.6182 6.29L19.2182 14.29C19.0913 14.713 18.7019 15.0027 18.2603 15.0027H6.00436V17.0027H17.0044V19.0027H5.00436C4.45207 19.0027 4.00436 18.5549 4.00436 18.0027V6.41686ZM6.00436 7.00265V13.0027H17.5163L19.3163 7.00265H6.00436ZM5.50436 23.0027C4.67593 23.0027 4.00436 22.3311 4.00436 21.5027C4.00436 20.6742 4.67593 20.0027 5.50436 20.0027C6.33279 20.0027 7.00436 20.6742 7.00436 21.5027C7.00436 22.3311 6.33279 23.0027 5.50436 23.0027ZM17.5044 23.0027C16.6759 23.0027 16.0044 22.3311 16.0044 21.5027C16.0044 20.6742 16.6759 20.0027 17.5044 20.0027C18.3328 20.0027 19.0044 20.6742 19.0044 21.5027C19.0044 22.3311 18.3328 23.0027 17.5044 23.0027Z">
                        </path>
                    </svg>
                    <img class="rounded-full w-12 h-12" src="" alt="">

                </div>
            </header>

            <!-- /////////////////////////////slider///////////////////////////////// -->


            <div class="w-full">
                <swiper :style="{
                    '--swiper-navigation-color': '#fff',
                    '--swiper-pagination-color': '#fff',
                }" :thumbs="{ swiper: thumbSwiper }" :spaceBetween="4" :navigation="true" :modules="modules"
                    class="mySwiper2">
                    <swiper-slide>
                        <img src="https://swiperjs.com/demos/images/nature-1.jpg" />
                    </swiper-slide><swiper-slide>
                        <img src="https://swiperjs.com/demos/images/nature-2.jpg" />
                    </swiper-slide><swiper-slide>
                        <img src="https://swiperjs.com/demos/images/nature-3.jpg" />
                    </swiper-slide><swiper-slide>
                        <img src="https://swiperjs.com/demos/images/nature-4.jpg" />
                    </swiper-slide>

                </swiper>

                <!-- ////////////////////////////////////////////////// -->

                <swiper @swiper="setThumbsSwiper" :spaceBetween="4" :slidesPerView="4" :freeMode="true"
                    :watchSlidesProgress="true" :modules="modules" class="mySwiper">
                    <swiper-slide><img src="https://swiperjs.com/demos/images/nature-1.jpg" />
                    </swiper-slide><swiper-slide>
                        <img src="https://swiperjs.com/demos/images/nature-2.jpg" />
                    </swiper-slide>
                    <swiper-slide>
                        <img src="https://swiperjs.com/demos/images/nature-3.jpg" />
                    </swiper-slide>
                    <swiper-slide>
                        <img src="https://swiperjs.com/demos/images/nature-4.jpg" />
                    </swiper-slide>


                </swiper>
            </div>


            <!-- ////////////////////////////////////////////////////prouduct////////////////////// -->


            <div></div>
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
