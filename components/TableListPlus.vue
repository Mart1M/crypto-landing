<template>
    <tr class="border-b border-darkgray">
        <td class="">
            <div class="flex space-x-4 pl-4">
                <h3 class="text-white font-medium">{{name}}</h3>
                <span class="font-medium text-gray">{{symbol}}</span>
            </div>       
        </td>
        <td class="">
            <p class="text-white text-right font-medium">${{price}}</p>
        </td>
        <td>
            <div class="flex pt-9 pb-9 justify-end text-red">
                <img src="../assets/icons/bx-caret-up.svg" alt="">
                <p>{{changeDaily}} %</p>
            </div>  
        </td>
        <td>
            <div class="flex evo-neg pt-9 pb-9 justify-end">
                <img src="../assets/icons/bx-caret-up.svg" alt="">
                <p>XX %</p>
            </div>  
        </td>
        <td class="">
            <p class="text-white text-right font-medium">${{marketCap}}</p>
        </td>
        <td class="">
            <p class="text-white text-right font-medium">${{volume}}</p>
        </td>
        <td class="pr-4">
            <p class="text-white text-right font-medium">${{cirSupply}}</p>
        </td>
    </tr>
</template>

<script>
export default {
    data() {
      return {
        currencies: []
      }
    },
    async fetch() {
      this.currencies = await fetch(
        'https://pro-api.coinmarketcap.com/v1/cryptocurrency/listings/latest?CMC_PRO_API_KEY=b6ac267d-71a4-456a-8fc9-52d2212787ee'
      ).then(res => res.json())
    },
    props:{
   name: String,
   symbol: String,
   price: Number,
   changeDaily: Number,
   changeWeekly: Number,
   marketCap: Number,
   volume: Number,
   cirSupply: Number
 }
    
  }
</script>
