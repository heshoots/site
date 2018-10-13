<template>
  <div class="projects">
    <BlogPage msg="Welcome to Your Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import BlogPage from '@/components/Blog.vue'; // @ is an alias to /src

@Component({
  components: {
    BlogPage,
  },
})
export default class Blog extends Vue {}
</script>
