<template>
  <div class="projects">
    <BlogPost :slug="this.$route.params.slug"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import BlogPost from '@/components/BlogPost.vue'; // @ is an alias to /src

@Component({
  components: {
    BlogPost,
  },
})
export default class Blog extends Vue {}
</script>
