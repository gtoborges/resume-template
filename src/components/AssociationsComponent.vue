<script setup>
import associations from '../assets/associations.json'
const props = defineProps(['lang', 'translations'])
</script>

<template>
  <section class="content-section">
    <header class="section-header">
      <h2>{{ props.translations.title }}</h2>
    </header>
    <div class="resume-item" v-for="association in associations[props.lang]">
      <h3 class="resume-item-title">
        <a :href="association.url">{{ association.organization }}</a>
      </h3>
      <h4 class="resume-item-details group">
        {{ association.role }} &bull; {{ association.year }}
      </h4>
      <p class="resume-item-copy" v-if="association.summary">{{ association.summary }}</p>
      <ul class="resume-item-list" v-if="association.bullet_points.length">
        <li v-for="point in association.bullet_points">{{ point }}</li>
      </ul>
    </div>
  </section>
</template>
