<script setup>
import links from '../assets/links.json'  
const props = defineProps(['lang', 'translations'])
</script>

<template>
  <section class="content-section">
    <header class="section-header">
      <h2>{{ props.translations.title }}</h2>
    </header>
    <div class="resume-item">
      <ul class="resume-item-list">
        <li v-for="link in links[props.lang]"><a :href="link.url">{{ link.description }}</a></li>
      </ul>
    </div>
  </section>
</template>
