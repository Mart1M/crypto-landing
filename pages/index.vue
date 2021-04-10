<template>
  <div class="container ">
    <nav class="nav p-3 flex items-center w-screen px-24">
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
      <p class="hero-subtitle">Join the world’s largest crypto exchange</p>
      <CTA-primary />
    </section>
    <section class="w-screen flex items-center price-list">
      <div class="price p-4 flex justify-between w-full">
        <div class="flex items-center space-x-4">
          <img src="../assets/img/bitcoin-btc-logo.png" alt="">
          <div class="flex flex-col">
            <p class="text-white font-medium">Bitcoin</p>
            <p class="indice font-medium">BTC</p>
          </div>
        </div>
        <div class="flex flex-col items-end">
          <p class="text-white font-bold ">$57,960.65</p>
          <div class="flex evo">
            <img src="../assets/icons/bx-caret-up.svg" alt="">
            <p>1.35%</p>
          </div>
        </div>
      </div>
      <div class="separator"></div>
      <div class="price p-4 flex justify-between w-full">
        <div class="flex items-center space-x-4">
          <img src="../assets/img/ethereum-eth-logo.png" alt="">
          <div class="flex flex-col">
            <p class="text-white font-medium">Ethereum</p>
            <p class="indice font-medium">ETH</p>
          </div>
        </div>
        <div class="flex flex-col items-end">
          <p class="text-white font-bold ">$57,960.65</p>
          <div class="flex evo">
            <img src="../assets/icons/bx-caret-up.svg" alt="">
            <p>1.35%</p>
          </div>
        </div>
      </div>
      <div class="separator"></div>
      <div class="price p-4 flex justify-between w-full">
        <div class="flex items-center space-x-4">
          <img src="../assets/img/binance-coin-bnb-logo.png" alt="">
          <div class="flex flex-col">
            <p class="text-white font-medium">Binance Coin</p>
            <p class="indice font-medium">BNB</p>
          </div>
        </div>
        <div class="flex flex-col items-end">
          <p class="text-white font-bold ">$57,960.65</p>
          <div class="flex evo">
            <img src="../assets/icons/bx-caret-up.svg" alt="">
            <p>1.35%</p>
          </div>
        </div>
      </div>
      <div class="separator"></div>
      <div class="price p-4 flex justify-between w-full">
        <div class="flex items-center space-x-4">
          <img src="../assets/img/xrp-xrp-logo.png" alt="">
          <div class="flex flex-col">
            <p class="text-white font-medium">XRP</p>
            <p class="indice font-medium">XRP</p>
          </div>
        </div>
        <div class="flex flex-col items-end">
          <p class="text-white font-bold ">$57,960.65</p>
          <div class="flex evo">
            <img src="../assets/icons/bx-caret-up.svg" alt="">
            <p>1.35%</p>
          </div>
        </div>
      </div>
      <div class="separator"></div>
      <div class="price p-4 flex justify-between w-full">
        <div class="flex items-center space-x-4">
          <img src="../assets/img/tether-usdt-logo.png" alt="">
          <div class="flex flex-col">
            <p class="text-white font-medium">Tether</p>
            <p class="indice font-medium">USDT</p>
          </div>
        </div>
        <div class="flex flex-col items-end">
          <p class="text-white font-bold ">$57,960.65</p>
          <div class="flex evo">
            <img src="../assets/icons/bx-caret-up.svg" alt="">
            <p>1.35%</p>
          </div>
        </div>
      </div>
      <div class="separator"></div>
      <div class="price p-4 flex justify-between w-full">
        <div class="flex items-center space-x-4">
          <img src="../assets/img/cardano-ada-logo.png" alt="">
          <div class="flex flex-col">
            <p class="text-white font-medium">Cardano</p>
            <p class="indice font-medium">ADA</p>
          </div>
        </div>
        <div class="flex flex-col items-end">
          <p class="text-white font-bold ">$57,960.65</p>
          <div class="flex evo">
            <img src="../assets/icons/bx-caret-up.svg" alt="">
            <p>1.35%</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {}
</script>

