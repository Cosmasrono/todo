<script setup>
/* import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'  */
</script>

<template>
  <main class=""> 
      <nav class="flex gap-5 justify-end py-3 text-white bg-green-500">
    
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav> 
      
  <RouterView />
  </main>
</template>

 