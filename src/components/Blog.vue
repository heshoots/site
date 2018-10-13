<template>
  <div id="blog-home">
      <h1>{{ page_title }}</h1>
      <!-- Create v-for and apply a key for Vue. Example is using a combination of the slug and index -->
      <div v-for="(post,index) in posts" :key="post.slug + '_' + index">
        <router-link :to="'/blog/' + post.slug">
          <md-card class="blogpost">
            <article class="media">
              <figure>
                <!-- Bind results using a ':' -->
                <!-- Use a v-if/else if their is a featured_image -->
                <img v-if="post.featured_image" :src="post.featured_image" alt="">
                <img v-else src="http://via.placeholder.com/250x250" alt="">
              </figure>
              <h2>{{ post.title }}</h2>
              <p>{{ post.summary }}</p>
            </article>
          </md-card>
        </router-link>
      </div>
  </div>
</template>
<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import { butter, ButterData} from '@/buttercms';

@Component
export default class HelloWorld extends Vue {
  @Prop() private slug!: string;
  private posts: object = [];
  private mounted() {
    this.getPosts();
  }

  private getPosts() {
    const vueM = this;
    butter.post.list({page: 1, page_size: 10}).then((resp: ButterData) => {
      vueM.posts = resp.data.data;
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
.about {
  padding: 2em;
  margin: 2em auto;
  max-width: 80em;
}
.cards {
  width: 40em;
  margin: 1em;
  display: inline-block;
}

.blogpost {
  padding: 0.5em;
  max-width: 60em;
  margin: 2em auto;
}

#blog-home {
  max-width: 80em;
  margin: auto auto;
}
</style>
