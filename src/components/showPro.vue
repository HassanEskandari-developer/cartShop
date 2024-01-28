<template>
  <div>
    <section class="w-[400px] h-auto border absolute  top-[87px] right-[37px] rounded-[20px] bg-[#ffedd5]">
        <div class=" gap-y-3 flex flex-col !mx-10 py-5">
            <img class="w-[200px] h-[100px] rounded-[15px]" :src="showPt.image" alt="">
        <h2>title : {{showPt.title}}</h2>
        <h2>price : {{showPt.discountedPrice}}</h2>
        <h2 class="text-gray-400 line-through">off : {{showPt.price}}</h2>
        <h2>quantity : {{showPt.quantity}}</h2>
        </div>
    </section>
  </div>
</template>

<script>
export default {
    props:{
        showPt:Object
    }
}
</script>

<style>

</style>