<script setup>
import associations from '../assets/associations.json'
const props = defineProps(['lang'])
</script>

<template>
  <section class="content-section">
    <header class="section-header">
      <h2>Associations</h2>
    </header>
    <div class="resume-item" v-for="association in associations[props.lang]">
      <h3 class="resume-item-title">
        <a :href="association.url">{{ association.organization }}</a>
      </h3>
      <h4 class="resume-item-details group">
        {{ association.role }} &bull; {{ association.year }}
      </h4>
      <p class="resume-item-copy">{{ association.summary }}</p>
    </div>
  </section>
</template>
