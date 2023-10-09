<script setup>
import { onBeforeMount, ref } from 'vue'
import HeaderComponent from './components/HeaderComponent.vue'
import ExperiencesComponent from './components/ExperiencesComponent.vue';
import EducationComponent from './components/EducationComponent.vue'
import ProjectsComponent from './components/ProjectsComponent.vue'
import resume_config from './assets/resume_config.json'

const lang = ref('')

onBeforeMount(() => {
  const params = new URLSearchParams(window.location.search)
  const preset_language = params.get('lang')
  const languages = Object.keys(resume_config.languages)
  if(languages.includes(preset_language)) lang.value = preset_language
  else lang.value = languages[0]  
  })
</script>

<template>
  <body class="theme-default wrapper">
    <select v-model="lang" name="languages" id="lang" style="float: right">
      <option v-for="language of Object.keys(resume_config.languages)" :value="language">{{resume_config.languages[language]}}</option>
    </select>
    <HeaderComponent :config="resume_config" :lang="lang"/>
    <ExperiencesComponent v-if="resume_config.resume_sections['experiences']" :lang="lang"/>
    <EducationComponent v-if="resume_config.resume_sections['education']" :lang="lang"/>
    <ProjectsComponent v-if="resume_config.resume_sections['projects']" :lang="lang"/>
    <footer class="page-footer">
      <p class="footer-line">Made by <a href="http://twitter.com/jglovier">@jglovier</a>. Fork me on <a href="https://github.com/jglovier/resume-template">GitHub</a>.</p>
    </footer>
  </body>
</template>

<style lang="scss">
// "Reset" styles and SCSS reusable components
@import "./scss/normalize";
@import "./scss/mixins";
@import "./scss/variables";

// Generic site base & layout styles
@import "./scss/base";
@import "./scss/layout";

// Layouts
@import "./scss/resume";
</style>
