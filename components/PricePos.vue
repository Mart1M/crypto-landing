<template>
    <div class="price p-4 flex justify-between w-full">
        <div class="flex items-center space-x-4">
          <img :src="logo" alt="logo" width="16px">
          <div class="flex flex-col">
            <p class="text-white font-medium">{{name}}</p>
            <p class="indice font-medium">{{symbol}}</p>
          </div>
        </div>
        <div class="flex flex-col items-end">
          <p class="text-white font-bold ">${{price}}</p>
            
          <div class="flex evo" >
            <img src="../assets/icons/bx-caret-up.svg" alt="">
            <p>{{change}} %</p>
          </div>

        </div>
      </div>
</template>

<script>

export default {
 props:{
   name: String,
   symbol: String,
   price: Number,
   change: Number,
   logo: {
     type: String,
     required: true
   }
 }
   
}
</script>


