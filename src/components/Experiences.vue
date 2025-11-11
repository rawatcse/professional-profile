<template>
  <section class="section" id="experiences">
    <div class="top-header"><h1>Experiences</h1></div>

    <div v-for="(expGroup, idx) in experiences" :key="idx">
      <h2>{{ expGroup.company }} ({{ expGroup.years }})</h2>
      <div class="experience-container">
        <div v-for="(item, i) in expGroup.projects" :key="i" class="experience-box">
          <h3>{{ item.title }}</h3>
          <p>{{ item.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue'
import ScrollReveal from 'scrollreveal'

const experiences = [
  {
    company: 'GB International',
    years: '2023-Present',
    projects: [
      {
        title: 'GB International',
        description:
          'Created APIs for multiple authentication, integrated Google Map, SMTP, Razorpay, and developed Vue templates with API integration.',
      },
    ],
  },
  {
    company: 'Hachiweb',
    years: '2020-2023',
    projects: [
      { title: 'RBL Bank Customer Offer', description: 'Created API of customer, offer, and response.' },
      { title: 'Happy Club United', description: 'Integrated SMTP and Google Map API.' },
      { title: 'Story Mantra', description: 'Developed APIs for categories, orders, and Razorpay payments.' },
      { title: 'Globiva feedback', description: 'Created token feedback API for internal devices.' },
      {
        title: 'Textflow',
        description:
          'Integrated Stripe, SendGrid email, team roles and project assignment features.',
      },
      { title: 'ODGTV Web', description: 'Integrated Agora API for live streaming.' },
    ],
  },
]

onMounted(() => {
  const sr = ScrollReveal({
    origin: 'top',
    distance: '80px',
    duration: 2000,
    reset: true,
  })
  sr.reveal('.experience-box', { interval: 200 })
})
</script>
