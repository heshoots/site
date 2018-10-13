<template>
  <div id="blog-post">
    <HeroImage :imagelocation="post.data.featured_image"/>
    <md-card class="cards">
      <md-content>
        <h1>{{ post.data.title }}</h1>
        <h4>{{ post.data.author.first_name }} {{ post.data.author.last_name }}</h4>
        <div v-html="post.data.body"></div>

        <router-link v-if="post.meta.previous_post" :to="/blog/ + post.meta.previous_post.slug" class="button">
          {{ post.meta.previous_post.title }}
        </router-link>
        <router-link v-if="post.meta.next_post" :to="/blog/ + post.meta.next_post.slug" class="button">
          {{ post.meta.next_post.title }}
        </router-link>
      </md-content>
    </md-card>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import HeroImage from './hero.vue';
import { butter, ButterData } from '@/buttercms';

@Component({components: {HeroImage}})
export default class BlogPost extends Vue {
  public post: object = {};
  @Prop() private slug!: string;

  private mounted() {
    const vueM = this;
    butter.post.retrieve(this.slug).then((resp: ButterData) => {
      vueM.post = resp.data;
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

.cards {
  max-width: 70em;
  margin: 1em;
  padding: 1em;
  display: inline-block;
}

#blog-post {
  text-color: #fff;
  padding: 2em;
  margin: auto auto;
  margin-top: 2em;
  max-width: 80em;
}
</style>
