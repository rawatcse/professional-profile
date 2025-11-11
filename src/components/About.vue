<template>
  <section class="section" id="about">
    <div class="top-header"><h1>About Me</h1></div>
    <div class="row">
      <div class="col">
        <div class="about-info">
          <h3>My introduction</h3>
          <p>
            Dynamic and results-oriented Full Stack Developer with more than two years of experience in crafting innovative web and application solutions. Proficient in both frontend and backend technologies, adept at translating complex concepts into user-friendly applications.
          </p>
        </div>
      </div>

      <div class="col">
        <div v-for="(box, index) in skills" :key="index" class="skills-box">
          <div class="skills-header"><h3>{{ box.title }}</h3></div>
          <div class="skills-list">
            <span v-for="(skill, i) in box.items" :key="i">{{ skill }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue'
import ScrollReveal from 'scrollreveal'

const skills = [
  { title: 'Frontend', items: ['HTML', 'CSS', 'JavaScript', 'Vue', 'Bootstrap'] },
  { title: 'Backend', items: ['PHP', 'Node'] },
  { title: 'Database', items: ['MySQL', 'PostgreSQL', 'MongoDB'] },
]

onMounted(() => {
  const sr = ScrollReveal({
    origin: 'right',
    distance: '80px',
    duration: 2000,
    reset: true,
  })
  sr.reveal('.skills-box', { delay: 100 })
})
</script>
