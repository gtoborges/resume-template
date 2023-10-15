<script setup>
import education from '../assets/education.json'
const props = defineProps(['lang', 'translations'])
</script>

<template>
  <section class="content-section">
    <header class="section-header">
      <h2>{{ props.translations.title }}</h2>
    </header>
    <div class="resume-item" v-for="education in education[props.lang]">
      <h3 class="resume-item-title">
        {{ education.institution }}
      </h3>
      <h4 class="resume-item-details group">
        {{ education.degree }} &bull; 
        <span v-if="education.duration.start">{{ education.duration.start }} &mdash;&nbsp;</span>
        <span v-if="education.duration.finish">{{ education.duration.finish }}</span> 
      </h4>
      <h5 class="resume-item-details award-title" v-if="education.award">
        {{ education.award }}
      </h5>
      <ul class="resume-item-list" v-if="education.awards.length">
        <li v-for="award in education.awards">{{ award }}</li>
      </ul>
      <p class="resume-item-copy">{{ education.summary }}</p>
    </div>
  </section>
</template>
