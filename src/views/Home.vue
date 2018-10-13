<template>
  <div class="home">
    <HomePage msg="Welcome to Your Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HomePage from '@/components/Home.vue'; // @ is an alias to /src

@Component({
  components: {
    HomePage,
  },
})
export default class Home extends Vue {}
</script>
