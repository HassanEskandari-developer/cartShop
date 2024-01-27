
<template>
    <div>
        <div class="">
            
            <swiper :style="{
                '--swiper-navigation-color': '#fff',
                '--swiper-pagination-color': '#fff',

            }" :thumbs="{ swiper: thumbSwiper }" :spaceBetween="4" :navigation="true" :modules="modules"
                class="mySwiper2 lg:rounded-[15px]">
                <swiper-slide class="!w-full">
                    <img :src=img1 />
                </swiper-slide><swiper-slide>
                    <img :src=img2 />
                </swiper-slide><swiper-slide>
                    <img :src=img3 />
                </swiper-slide><swiper-slide>
                    <img :src=img4 />
                </swiper-slide>

            </swiper>

            <!-- ////////////////////////////////////////////////// -->

            <swiper @swiper="setThumbsSwiper" :spaceBetween="15" height="500px" :slidesPerView="4" :freeMode="true"
                :watchSlidesProgress="true" :modules="modules" class="mySwiper mt-8 rounded-[15px] !hidden lg:!flex">
                <swiper-slide><img :src=img1_2  class="rounded-[15px]"/>
                </swiper-slide><swiper-slide>
                    <img :src=img2_2 class="rounded-[15px]"/>
                </swiper-slide>
                <swiper-slide>
                    <img :src=img3_2 class="rounded-[15px]"/>
                </swiper-slide>
                <swiper-slide>
                    <img :src=img4_2 class="rounded-[15px]"/>
                </swiper-slide>


            </swiper>
        </div>

    </div>
</template>
  
  
  
  
  
<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/thumbs';

import { FreeMode, Navigation, Thumbs } from 'swiper/modules';
export default {
    data() {
        return {
            img1: '/public/images/image-product-1.jpg',
            img2: '/public/images/image-product-2.jpg',
            img3: '/public/images/image-product-3.jpg',
            img4: '/public/images/image-product-4.jpg',
            img1_2: '/public/images/image-product-1-thumbnail.jpg',
            img2_2: '/public/images/image-product-2-thumbnail.jpg',
            img3_2: '/public/images/image-product-3-thumbnail.jpg',
            img4_2: '/public/images/image-product-4-thumbnail.jpg',
            modules: [Navigation, Thumbs],
            thumbSwiper: null

        }
    },

    components: {
        Swiper,
        SwiperSlide,
    },

    methods: {
        setThumbsSwiper(swiper) {
            this.thumbSwiper = swiper
        }

    },
}
</script>
  
  
  
  
<style scoped>
.swiper-wrapper {
    width: 100%;
    max-width: 100%;
    max-height: 100vh;
    min-height: 0;
    min-width: 0;
}

</style>