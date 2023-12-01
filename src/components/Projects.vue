<script setup>
    import Project from './Project.vue';
    import { ref, onMounted } from 'vue';
    import projectData from '../assets/projects.json';
    const projects =  ref(projectData);

</script>

<template>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-4" style="grid-auto-flow: dense; grid-template-rows: repeat(auto-fill, minmax(0, 1fr));">
    <Project
      v-for="p in projects"
      :key="p.name"
      :name="p.name"
      :description="p.description"
      :repo="p.repo"
      :lang="p.lang"
      :stars="p.stars"
    />
  </div>
</template>

