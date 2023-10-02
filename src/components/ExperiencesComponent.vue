<script setup>
import experiences from '../assets/experiences.json' 
const props = defineProps(['lang'])
</script>

<template>
  <section class="content-section">
    <header class="section-header">
      <h2>Experience</h2>
    </header>
    <div class="resume-item" v-for="xp in experiences[props.lang]">
      <h3 class="resume-item-title">
        {{ xp.company }}
      </h3>
      <h4 class="resume-item-details">
        {{ xp.position }} &bull; {{ xp.duration.start }} &mdash; {{ xp.duration.finish }} 
      </h4>
      <p class="resume-item-copy">{{ xp.summary }}</p>
      <ul class="resume-item-list" v-if="xp.bullet_points">
        <li v-for="bullet_points of xp.bullet_points">{{bullet_points}}</li>
      </ul>
    </div>  
  </section>
</template>
