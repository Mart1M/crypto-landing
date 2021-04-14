<template>
  <div>
    <Navigation />

    <section class="hero flex justify-center items-center w-screen h-72 flex-col space-y-5">
      <h1 class="text-white">Buy & Sell Crypto in seconds</h1>
      <p class="subtitle">Join the world’s largest crypto exchange</p>
      <CTA-primary />
    </section>
    <section class="w-screen grid grid-cols-6 divide-x divide-darkgray">
        <div class="w-full price-list" v-for="currency in currencies.data.slice(0, 6)">
          <div v-if="currency.quote.USD.percent_change_24h > 0">
            <PricePos :logo="'https://cryptologos.cc/logos/' + currency.name.toLowerCase().replace(/ /g,'-') + '-' + currency.symbol.toLowerCase() + '-logo.png'" :name="currency.name" :symbol="currency.symbol" :price="Math.round(currency.quote.USD.price*100)/100" :change="Math.round(currency.quote.USD.percent_change_24h *100)/100" />
          </div>
          <div v-else>
            <PriceNeg :logo="'https://cryptologos.cc/logos/' + currency.name.toLowerCase().replace(/ /g,'-') + '-' + currency.symbol.toLowerCase() + '-logo.png'" :name="currency.name" :symbol="currency.symbol" :price="Math.round(currency.quote.USD.price*100)/100" :change="Math.round(currency.quote.USD.percent_change_24h *100)/100" />
          </div>
        </div>
    </section>

    <section class="grid grid-cols-2 px-40 gap-8 w-screen py-40">
      <section class="flex flex-col justify-center space-y-4">
        <h1 class="text-white">Trade. Anywhere.</h1>
        <p class="subtitle">Compatible with multiple devices, start trading with safety and convenience</p>
        <div class="flex space-x-8">
          <img src="../assets/icons/bxl-apple.svg" alt="">
          <img src="../assets/icons/bxl-android.svg" alt="">
          <img src="../assets/icons/bxl-play.svg" alt="">
          <img src="../assets/icons/bxl-win.svg" alt="">
          <img src="../assets/icons/bxl-linux.svg" alt="">
        </div>
      </section>
      <section class="flex justify-end w-full">
        <img src="../assets/img/illu.png" alt="">
      </section>
    </section>

    <section class="w-screen flex flex-col items-center">
      <h1 class="text-white pb-8">100+ Cryptocurrency Assets</h1>
      <img src="../assets/img/cryptos.png" alt="" width="700px">
      
      
      
    </section>
    
  </div>
</template>




<script>
import PricePos from "../components/PricePos.vue";
import PriceNeg from "../components/PriceNeg.vue";
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
    }
  }

  

  
</script>