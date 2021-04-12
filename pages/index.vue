<template>
  <div class="container ">
    <nav class="nav p-3 flex items-center w-screen px-40">
      <img src="../assets/img/log.png" alt="">
      <ul class="flex space-x-12 text-white">
        <li><a href="">Buy Crypto</a></li>
        <li><a href="">Markets</a></li>
        <li><a href="">Trade</a></li>
        <li><a href="">Derivatives</a></li>
        <li><a href="">Finance</a></li>
      </ul>
      <div class="flex space-x-4 items-center">
        <a class="text-white" href="#">Log In</a>
        <a class="cta-little px-4 text-white py-2 rounded-lg" href="#">Register</a>
        <div class="flex items-center space-x-2">
        <p class="text-white">USD $</p>
        <img src="../assets/icons/bx-caret-down.svg" alt="" srcset="">
        </div>
      </div>
      
    </nav>
    <section class="hero flex justify-center items-center w-screen h-72 flex-col space-y-5">
      <h1 class="text-white">Buy & Sell Crypto in seconds</h1>
      <p class="subtitle">Join the world’s largest crypto exchange</p>
      <CTA-primary />
    </section>
    <section class="w-screen flex items-center price-list">


      <div v-if="currencies.data[0].quote.USD.percent_change_24h > 0" class="w-full">
        <PricePos logo="https://cryptologos.cc/logos/bitcoin-btc-logo.png" :name="currencies.data[0].name" :symbol="currencies.data[0].symbol" :price="Math.round(currencies.data[0].quote.USD.price*100)/100" :change="Math.round(currencies.data[0].quote.USD.percent_change_24h *100)/100" />
      </div>
      <div v-else class="w-full">
        <PriceNeg logo="https://cryptologos.cc/logos/bitcoin-btc-logo.png" :name="currencies.data[0].name" :symbol="currencies.data[0].symbol" :price="Math.round(currencies.data[0].quote.USD.price*100)/100" :change="Math.round(currencies.data[0].quote.USD.percent_change_24h *100)/100" />
      </div>
      
      <div class="separator"></div>

      <div v-if="currencies.data[1].quote.USD.percent_change_24h > 0" class="w-full">
        <PricePos logo="https://cryptologos.cc/logos/ethereum-eth-logo.png" :name="currencies.data[1].name" :symbol="currencies.data[1].symbol" :price="Math.round(currencies.data[1].quote.USD.price*100)/100" :change="Math.round(currencies.data[1].quote.USD.percent_change_24h *100)/100" />
      </div>
      <div v-else class="w-full">
        <PriceNeg logo="https://cryptologos.cc/logos/ethereum-eth-logo.png" :name="currencies.data[1].name" :symbol="currencies.data[1].symbol" :price="Math.round(currencies.data[1].quote.USD.price*100)/100" :change="Math.round(currencies.data[1].quote.USD.percent_change_24h *100)/100" />
      </div>

      <div class="separator"></div>

      <div v-if="currencies.data[2].quote.USD.percent_change_24h > 0" class="w-full">
        <PricePos logo="https://cryptologos.cc/logos/binance-coin-bnb-logo.png" :name="currencies.data[2].name" :symbol="currencies.data[2].symbol" :price="Math.round(currencies.data[2].quote.USD.price*100)/100" :change="Math.round(currencies.data[2].quote.USD.percent_change_24h *100)/100" />
      </div>
      <div v-else class="w-full">
        <PriceNeg logo="https://cryptologos.cc/logos/binance-coin-bnb-logo.png" :name="currencies.data[2].name" :symbol="currencies.data[2].symbol" :price="Math.round(currencies.data[2].quote.USD.price*100)/100" :change="Math.round(currencies.data[2].quote.USD.percent_change_24h *100)/100" />
      </div>

      <div class="separator"></div>

      <div v-if="currencies.data[3].quote.USD.percent_change_24h > 0" class="w-full">
        <PricePos logo="https://cryptologos.cc/logos/xrp-xrp-logo.png" :name="currencies.data[3].name" :symbol="currencies.data[3].symbol" :price="Math.round(currencies.data[3].quote.USD.price*100)/100" :change="Math.round(currencies.data[3].quote.USD.percent_change_24h *100)/100" />
      </div>
      <div v-else class="w-full">
        <PriceNeg logo="https://cryptologos.cc/logos/xrp-xrp-logo.png" :name="currencies.data[3].name" :symbol="currencies.data[3].symbol" :price="Math.round(currencies.data[3].quote.USD.price*100)/100" :change="Math.round(currencies.data[3].quote.USD.percent_change_24h *100)/100" />
      </div>

      <div class="separator"></div>

      <div v-if="currencies.data[4].quote.USD.percent_change_24h > 0" class="w-full">
        <PricePos logo="https://cryptologos.cc/logos/tether-usdt-logo.png" :name="currencies.data[4].name" :symbol="currencies.data[4].symbol" :price="Math.round(currencies.data[4].quote.USD.price*100)/100" :change="Math.round(currencies.data[4].quote.USD.percent_change_24h *100)/100" />
      </div>
      <div v-else class="w-full">
        <PriceNeg logo="https://cryptologos.cc/logos/tether-usdt-logo.png" :name="currencies.data[4].name" :symbol="currencies.data[4].symbol" :price="Math.round(currencies.data[4].quote.USD.price*100)/100" :change="Math.round(currencies.data[4].quote.USD.percent_change_24h *100)/100" />
      </div>

      <div class="separator"></div>

      <div v-if="currencies.data[5].quote.USD.percent_change_24h > 0" class="w-full">
        <PricePos logo="https://cryptologos.cc/logos/cardano-ada-logo.png" :name="currencies.data[5].name" :symbol="currencies.data[5].symbol" :price="Math.round(currencies.data[5].quote.USD.price*100)/100" :change="Math.round(currencies.data[5].quote.USD.percent_change_24h *100)/100" />
      </div>
      <div v-else class="w-full">
        <PriceNeg logo="https://cryptologos.cc/logos/cardano-ada-logo.png" :name="currencies.data[5].name" :symbol="currencies.data[5].symbol" :price="Math.round(currencies.data[5].quote.USD.price*100)/100" :change="Math.round(currencies.data[5].quote.USD.percent_change_24h *100)/100" />
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