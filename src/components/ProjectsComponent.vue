<script setup>
import projects from '../assets/projects.json'
const props = defineProps(['lang', 'translations'])
</script>

<template>
  <section class="content-section">
    <header class="section-header">
      <h2>{{ props.translations.title }}</h2>
    </header>
    <div class="resume-item" v-for="project in projects[props.lang]">
      <h3 class="resume-item-title">
        {{ project.project }}
      </h3>
      <h4 class="resume-item-details group">
        {{ project.role }} &bull; {{ project.duration.start }} &mdash; {{ project.duration.finish }} 
      </h4>
      <p class="resume-item-copy">{{ project.description }}</p>
    </div>
  </section>
</template>
