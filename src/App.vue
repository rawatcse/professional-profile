<template>
  <div class="container">
    <HeaderNav />
    <main class="wrapper">
      <Featured />
      <About />
      <Experiences />
    </main>
    <FooterComp />
  </div>
</template>

<script setup>
import HeaderNav from './components/HeaderNav.vue'
import Featured from './components/Featured.vue'
import About from './components/About.vue'
import Experiences from './components/Experiences.vue'
import FooterComp from './components/FooterComp.vue'
</script>

<style>
html { scroll-behavior: smooth; }
</style>
