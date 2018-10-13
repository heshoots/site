<template>
  <div class="projects">
    <ProjectPage msg="Welcome to Your Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import ProjectPage from '@/components/Projects.vue'; // @ is an alias to /src

@Component({
  components: {
    ProjectPage,
  },
})
export default class Projects extends Vue {}
</script>
