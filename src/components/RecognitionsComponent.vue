<script setup>
import recognitions from '../assets/recognitions.json'
const props = defineProps(['lang'])
</script>

<template>
  <section class="content-section">
    <header class="section-header">
      <h2>Recognitions</h2>
    </header>
    <div class="resume-item" v-for="recognition in recognitions[props.lang]">
      <h3 class="resume-item-title">
        {{ recognition.award }}
      </h3>
      <h4 class="resume-item-details group">
        {{ recognition.organization }} &bull; {{ recognition.year }}
      </h4>
      <p class="resume-item-copy">{{ recognition.summary }}</p>
    </div>
  </section>
</template>
