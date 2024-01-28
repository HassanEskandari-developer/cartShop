
<template>
  <div>
    <h2 class="text-[#ea580c] font-bold">SNEAKER COMOPNY</h2>
    <h1 class="text-black lg:leading-10 text-[40px] font-[900]">
      Fall Limited Edition Sneaker
    </h1>
    <p class="text-gray-400 text-[16px]">
      These low-profile sneakers are your perfect casual wear companion.
      Featuring a durable rubber outer sole, they’ll withstand everything the
      weather can offer.
    </p>
    <div class="flex lg:flex-col justify-between items-center lg:items-start">
      <div class="flex gap-x-2 lg:gap-x-5 justify-start items-center">
        <span class="text-black font-bold text-[30px]">$125.00</span>
        <span
          class="border text-[#f59e0b] bg-[#ffedd5] font-bold rounded-[10px] text-[18px] w-12 text-center"
          >50%</span
        >
      </div>
      <span class="text-gray-400 line-through font-bold">$250.00</span>
    </div>
    <div
      class="flex gap-x-12 mt-5 flex-col items-center lg:flex-row gap-y-5 lg:gap-y-0"
    >

    
      <div
      
        v-if="qty > 0"
        class="flex w-72 lg:w-[150px] lg:justify-start !justify-center gap-20 lg:gap-x-7 rounded-[15px] h-14 mt-2 items-center bg-gray-100"
      >
        <button class="text-[#f59e0b] text-[25px] font-bold" @click="maines">
          -
        </button>
        <span class="font-bold">{{ qty }}</span>
        <button class="text-[#f59e0b] text-[25px]" @click="pluse">+</button>
      </div>
      <button
        v-else
        @click="pluse"
        class="text-white bg-[#ea580c] w-full h-14 lg:w-60 lg:h-16 rounded-[10px] flex justify-center items-center gap-x-3 mb-2"
      >
        <svg
          class="w-[30px] h-[25px]"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          fill="currentColor"
        >
          <path
            d="M4.00436 6.41686L0.761719 3.17422L2.17593 1.76001L5.41857 5.00265H20.6603C21.2126 5.00265 21.6603 5.45037 21.6603 6.00265C21.6603 6.09997 21.6461 6.19678 21.6182 6.29L19.2182 14.29C19.0913 14.713 18.7019 15.0027 18.2603 15.0027H6.00436V17.0027H17.0044V19.0027H5.00436C4.45207 19.0027 4.00436 18.5549 4.00436 18.0027V6.41686ZM6.00436 7.00265V13.0027H17.5163L19.3163 7.00265H6.00436ZM5.50436 23.0027C4.67593 23.0027 4.00436 22.3311 4.00436 21.5027C4.00436 20.6742 4.67593 20.0027 5.50436 20.0027C6.33279 20.0027 7.00436 20.6742 7.00436 21.5027C7.00436 22.3311 6.33279 23.0027 5.50436 23.0027ZM17.5044 23.0027C16.6759 23.0027 16.0044 22.3311 16.0044 21.5027C16.0044 20.6742 16.6759 20.0027 17.5044 20.0027C18.3328 20.0027 19.0044 20.6742 19.0044 21.5027C19.0044 22.3311 18.3328 23.0027 17.5044 23.0027Z"
          ></path>
        </svg>
        <span class="font-bold"> Add to cart</span>
      </button>
    </div>
  </div>
</template>
  
  
  
  
  
<script>
export default {
  emits: ["getQuantity"],
  data() {
    return {
      qty: 0,
    };
  },
  props: {
    quanCart: Object,
  },
  watch: {
    // quanCart: {
    //   immediate: true,
    //   deep: true,
    //   handler(val) {
    //     if (val) {
    //       this.qty = val;
    //       console.log(this.qty);
    //     }
    //   },
    // },
    quanCart: {
      handler(val) {
        if (val) {
          this.qty = val;
          console.log(this.qty);
        }
      },
    },
    qty: function (val) {
      this.$emit("getQuantity", val);
    },
    stopnumber: function () {
      this.qty;
    },
  },
  methods: {
    pluse() {
      this.qty++;
      if (this.qty > 4) {
        this.qty = 4;
        alert("سقف خرید پر شده است");
      }
    },
    maines() {
      this.qty--;
    },
  },
};
</script>
  
  
  
  
<style></style>