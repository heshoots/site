<template>
  <div class="hello">
    <md-card v-for="project in projects.data.data.fields.projects" v-key="project.name" md-with-hover class="cards">
      <md-card-header>
        <md-card-header-text>
          <div class="md-title">{{ project.name }}</div>
          <div class="md-subhead">{{ project.description }}</div>
        </md-card-header-text>
      </md-card-header>
      <md-card-actions>
        <md-button v-if="project.code_link != ''" :href="project.code_link">View Code</md-button>
        <md-button v-if="project.live_link != ''" :href="project.live_link">View Live</md-button>
      </md-card-actions>
    </md-card>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import HeroImage from './hero.vue';
import { butter, ButterData } from '@/buttercms';

@Component({components: {HeroImage}})
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
  private projects: ButterData = { data: { data: {}}};
  private mounted() {
    const vueM = this;
    butter.page.retrieve('*', 'projects').then((res: ButterData) => {
      vueM.projects = res;
    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.hello {
  padding: 1em auto;
  display: flex;
  flex-wrap: wrap;
}

.cards {
  margin: 1em;
  flex-grow: 1;
  overflow-x: auto;
}
</style>
