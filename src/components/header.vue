<template>
  <md-toolbar>
    <div class="md-toolbar-section-start">
      <router-link to="/">
        <md-button>
          <h3>Max Prettyjohns</h3>
        </md-button>
      </router-link>
    </div>
    <div class="md-toolbar-section-end">
      <router-link to="/projects">
        <md-button>
          <h2>Projects</h2>
        </md-button>
      </router-link>
      <router-link to="/blog">
        <md-button>
          <h2>Blog</h2>
        </md-button>
      </router-link>
    </div>
  </md-toolbar>
</template>
<script>
import { Component, Prop, Vue } from 'vue-property-decorator';
@Component
export default class Header extends Vue {}
</script>
