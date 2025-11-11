<template>
  <section class="featured-box" id="home">
    <div class="featured-text">
      <div class="featured-text-card"><span>Rahul Rawat</span></div>
      <div class="featured-name">
        <p>I'm <span class="typedText"></span></p>
      </div>
      <div class="featured-text-info">
        <p>
          Experienced full stack developer passionate about staying updated with the latest technologies and trends.
        </p>
      </div>
      <div class="featured-text-btn">
        <a href="#contact"><button class="btn blue-btn">Contact me</button></a>
      </div>
    </div>

    <div class="featured-image">
      <div class="image">
        <!-- ✅ Use imported image here -->
        <img :src="homeImage" alt="avatar" />
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue'
import Typed from 'typed.js'
import ScrollReveal from 'scrollreveal'

// ✅ Import image correctly
import homeImage from '@/assets/images/home.png'

onMounted(() => {
  new Typed('.typedText', {
    strings: ['Software Developer', 'Web Developer'],
    loop: true,
    typeSpeed: 100,
    backSpeed: 80,
    backDelay: 2000,
  })

  const sr = ScrollReveal({
    origin: 'top',
    distance: '80px',
    duration: 2000,
    reset: true,
  })

  sr.reveal('.featured-text-card')
  sr.reveal('.featured-name', { delay: 100 })
  sr.reveal('.featured-text-info', { delay: 200 })
  sr.reveal('.featured-text-btn', { delay: 300 })
  sr.reveal('.featured-image', { delay: 400 })
})
</script>
