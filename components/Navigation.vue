<template>
    <nav class="nav p-3 flex items-center w-screen px-40">
        <NuxtLink to="/"><img src="../assets/img/log.png" alt=""></NuxtLink>
      
      <ul class="flex space-x-12 text-white">
        <li>
            <NuxtLink to="/">Buy Crypto</NuxtLink>
        </li>
        <li><NuxtLink to="/markets">Markets</NuxtLink></li>
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
</template>