<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import SideBar from './components/SideBar.vue'
</script>

<template>
  <div class="row">
    
    <div > <SideBar/></div>
    <div class="col" style="margin-left: 15rem;"><RouterView></RouterView></div>
  </div>
</template>