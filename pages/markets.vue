<template>
    <div>
        <Navigation />

        <!-- <section class="w-screen flex items-center space-x-8 px-40 pt-8" >
      <div v-if="currencies.data[0].quote.USD.percent_change_24h > 0" class="w-full price-list">
        <PricePos logo="https://cryptologos.cc/logos/bitcoin-btc-logo.png" :name="currencies.data[0].name" :symbol="currencies.data[0].symbol" :price="Math.round(currencies.data[0].quote.USD.price*100)/100" :change="Math.round(currencies.data[0].quote.USD.percent_change_24h *100)/100" />
      </div>
      <div v-else class="w-full price-list">
        <PriceNeg logo="https://cryptologos.cc/logos/bitcoin-btc-logo.png" :name="currencies.data[0].name" :symbol="currencies.data[0].symbol" :price="Math.round(currencies.data[0].quote.USD.price*100)/100" :change="Math.round(currencies.data[0].quote.USD.percent_change_24h *100)/100" />
      </div>
      

      <div v-if="currencies.data[1].quote.USD.percent_change_24h > 0" class="w-full price-list">
        <PricePos logo="https://cryptologos.cc/logos/ethereum-eth-logo.png" :name="currencies.data[1].name" :symbol="currencies.data[1].symbol" :price="Math.round(currencies.data[1].quote.USD.price*100)/100" :change="Math.round(currencies.data[1].quote.USD.percent_change_24h *100)/100" />
      </div>
      <div v-else class="w-full price-list">
        <PriceNeg logo="https://cryptologos.cc/logos/ethereum-eth-logo.png" :name="currencies.data[1].name" :symbol="currencies.data[1].symbol" :price="Math.round(currencies.data[1].quote.USD.price*100)/100" :change="Math.round(currencies.data[1].quote.USD.percent_change_24h *100)/100" />
      </div>

      <div v-if="currencies.data[2].quote.USD.percent_change_24h > 0" class="w-full price-list">
        <PricePos logo="https://cryptologos.cc/logos/binance-coin-bnb-logo.png" :name="currencies.data[2].name" :symbol="currencies.data[2].symbol" :price="Math.round(currencies.data[2].quote.USD.price*100)/100" :change="Math.round(currencies.data[2].quote.USD.percent_change_24h *100)/100" />
      </div>
      <div v-else class="w-full price-list">
        <PriceNeg logo="https://cryptologos.cc/logos/binance-coin-bnb-logo.png" :name="currencies.data[2].name" :symbol="currencies.data[2].symbol" :price="Math.round(currencies.data[2].quote.USD.price*100)/100" :change="Math.round(currencies.data[2].quote.USD.percent_change_24h *100)/100" />
      </div>



      <div v-if="currencies.data[3].quote.USD.percent_change_24h > 0" class="w-full price-list">
        <PricePos logo="https://cryptologos.cc/logos/xrp-xrp-logo.png" :name="currencies.data[3].name" :symbol="currencies.data[3].symbol" :price="Math.round(currencies.data[3].quote.USD.price*100)/100" :change="Math.round(currencies.data[3].quote.USD.percent_change_24h *100)/100" />
      </div>
      <div v-else class="w-full price-list">
        <PriceNeg logo="https://cryptologos.cc/logos/xrp-xrp-logo.png" :name="currencies.data[3].name" :symbol="currencies.data[3].symbol" :price="Math.round(currencies.data[3].quote.USD.price*100)/100" :change="Math.round(currencies.data[3].quote.USD.percent_change_24h *100)/100" />
      </div>    
      
    </section> -->

    <section class="w-screen flex items-center flex-row space-x-8 px-40 pt-8">
        <div class="w-full price-list" v-for="currency in currencies.data.slice(0, 5)">
                <div v-if="currency.quote.USD.percent_change_24h > 0">
                <PricePos :logo="'https://cryptologos.cc/logos/' + currency.name.toLowerCase().replace(/ /g,'-') + '-' + currency.symbol.toLowerCase() + '-logo.png'" :name="currency.name" :symbol="currency.symbol" :price="Math.round(currency.quote.USD.price*100)/100" :change="Math.round(currency.quote.USD.percent_change_24h *100)/100" />
            </div>
            <div v-else>
                <PriceNeg :logo="'https://cryptologos.cc/logos/' + currency.name.toLowerCase().replace(/ /g,'-') + '-' + currency.symbol.toLowerCase() + '-logo.png'" :name="currency.name" :symbol="currency.symbol" :price="Math.round(currency.quote.USD.price*100)/100" :change="Math.round(currency.quote.USD.percent_change_24h *100)/100" />
            </div>
        </div>
    </section>
<section class="w-screen px-40 pt-8">
    <table class="table-auto w-full">
        <thead class="indice font-medium border-b border-darkgray">
            <tr>
            <th class="pt-4 pb-4 pl-4 text-left">Name</th>
            <th class="text-right">Price</th>
            <th class="text-right">24h %</th>
            <th class="text-right">Market Cap</th>
            <th class="text-right">Volume(24h)</th>
            <th class="text-right pr-4">Circulating Supply</th>
            </tr>
        </thead>
        <tbody v-for="currency in currencies.data.slice(0, 20)" >
                <TableList :logo="'https://cryptologos.cc/logos/' + currency.name.toLowerCase().replace(/ /g,'-') + '-' + currency.symbol.toLowerCase() + '-logo.png'" :name="currency.name" :symbol="currency.symbol" :price="Math.round(currency.quote.USD.price*100)/100" :changeDaily="Math.round(currency.quote.USD.percent_change_24h *100)/100" :marketCap="Math.round(currency.quote.USD.market_cap)" :volume="Math.round(currency.quote.USD.volume_24h)" :cirSupply="currency.circulating_supply"/>
            
        </tbody>

    </table>

</section>
    
    
    </div>
</template>

<script>
import PricePos from "../components/PricePos.vue";
import PriceNeg from "../components/PriceNeg.vue";
import TableList from "../components/TableList.vue";
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