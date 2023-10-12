<script setup>
import skills from '../assets/skills.json'
const props = defineProps(['lang', 'translations'])
</script>

<template>
  <section class="content-section">
    <header class="section-header">
      <h2>{{ props.translations.title }}</h2>
    </header>
    <div class="resume-item" v-for="skill in skills[props.lang]">
      <h4 class="resume-item-details">{{ skill.name }}</h4>
      <p class="resume-item-copy">{{ skill.description }}</p>
    </div>
  </section>
</template>
