<script>
import Header from "../components/Header.vue";
import Slider from "../components/Slider.vue";
import Product from "../components/Product.vue";


export default {
  data() {
    return {
      customProduct: {
        title: "Fall Limited Edition Sneaker",
        image: "/images/image-product-1.jpg",
        price: 250,
        discountedPrice: 125,
        quantity: 0,
      },
    };
  },
  mounted(){
    this.checkLocalStorge()
  },

  components: {
    Header,
    Slider,
    Product,
    
  },

  watch: {},
  methods: {
    checkQuantity(qty) {
      this.customProduct.quantity=qty
      this.localDate()
    },
    localDate() {
        if(this.customProduct.quantity==0){
            localStorage.removeItem('product')
        }else{
            localStorage.setItem("product", JSON.stringify(this.customProduct));

        }

      //   localStorage.setItem("tittel", this.title);
      //   localStorage.setItem("img", this.image);
      //   localStorage.setItem("pric", this.price);
      //   localStorage.setItem("discoun", this.discountedPrice);
    },

    checkLocalStorge(){
        let prouduct =localStorage.getItem('product')
        prouduct = JSON.parse(prouduct)
        // this.customProduct.quantity=prouduct.quantity
        if(prouduct && prouduct.quantity){
            this.customProduct.quantity=prouduct.quantity
        }
        console.log(prouduct);

        
    }
  },
};
</script>




<template>
  <main>
    <section class="w-full max-h-screen flex flex-col">
      <!-- ////////////////////////////header//////////////////////////// -->
      <Header :customProduct="customProduct"  class="w-full"></Header>

      <div
        class="w-full flex justify-center items-center gap-x-40 flex-col lg:flex-row gap-y-7 lg:gap-y-0 lg:!mt-40"
      >
        <!-- /////////////////////////////slider///////////////////////////////// -->
        <div class="w-full lg:w-1/4">
          <Slider></Slider>
        </div>
        <!-- ////////////////////////////////////////////////////prouduct////////////////////// -->
        <div
          class="w-full lg:w-1/4 flex justify-center items-center lg:items-start flex-col"
        >
          <Product
            @getQuantity="checkQuantity" :quanCart="customProduct.quantity"
            class="!gap-y-1 flex flex-col justify-center !mx-4"
          ></Product>
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
