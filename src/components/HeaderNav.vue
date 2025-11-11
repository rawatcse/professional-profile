<template>
  <nav id="header" :class="{ shadow: hasShadow }">
    <div class="nav-logo">
      <p class="nav-name">Rahul Rawat</p>
      <span></span>
    </div>
    <div :class="['nav-menu', { responsive: menuOpen }]" id="myNavMenu">
      <ul class="nav_menu_list">
        <li v-for="link in links" :key="link.id" class="nav_list">
          <a
            :href="link.href"
            class="nav-link"
            :class="{ 'active-link': activeSection === link.href.slice(1) }"
          >
            {{ link.name }}
          </a>
          <div class="circle"></div>
        </li>
      </ul>
    </div>
    <div class="nav-menu-btn" @click="menuOpen = !menuOpen">
      <i class="uil uil-bars"></i>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const menuOpen = ref(false)
const hasShadow = ref(false)
const activeSection = ref('')
const links = [
  { id: 1, name: 'Home', href: '#home' },
  { id: 2, name: 'About', href: '#about' },
  { id: 3, name: 'Projects', href: '#experiences' },
]

const handleScroll = () => {
  hasShadow.value = window.scrollY > 50
  const sections = document.querySelectorAll('section[id]')
  const scrollY = window.scrollY
  sections.forEach((current) => {
    const sectionHeight = current.offsetHeight
    const sectionTop = current.offsetTop - 50
    const id = current.getAttribute('id')
    if (scrollY > sectionTop && scrollY <= sectionTop + sectionHeight) {
      activeSection.value = id
    }
  })
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<style scoped>
.shadow {
  box-shadow: 0 1px 6px rgba(0, 0, 0, 0.1);
  height: 70px !important;
  line-height: 70px !important;
}
</style>
