<template>
<div>
<ul>
    <li v-for="currency in currencies.data.slice(0, 5)" :key="currency.name">
        <p class="text-white">{{currency.name}}</p>
        <img :src="'https://cryptologos.cc/logos/' + currency.name.toLowerCase().replace(/ /g,'-') + '-' + currency.symbol.toLowerCase() + '-logo.png'" alt="" width='20px' srcset="">

    </li>
</ul>
</div>
    

    
</template>

<script>
export default {
    data() {
      return {
        currencies: [],
      }
    },
    async fetch() {
      this.currencies = await fetch(
        'https://pro-api.coinmarketcap.com/v1/cryptocurrency/listings/latest?CMC_PRO_API_KEY=b6ac267d-71a4-456a-8fc9-52d2212787ee'
      ).then(res => res.json());
    }
    
  }
</script>