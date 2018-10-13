<template>
  <div class="hello">
    <HeroImage imagelocation="/mountain.jpg" alt="mountain at sunset" text="Welcome to the personal page of Max Prettyjohns"></HeroImage>
    <md-card class="about">
      <md-content md-tag="section">
        <h2>About me</h2>
        <p>Hi, I am a full stack developer who works at <a href="https://epimorphics.com">epimorphics</a>. Here I will post the projects I am working on and blog posts.</p>
      </md-content>
    </md-card>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import HeroImage from './hero.vue';

@Component({components: {HeroImage}})
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
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
.hero-image {
    /* Use "linear-gradient" to add a darken background effect to the image (photographer.jpg). This will make the text easier to read */
    background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url("/mountain.jpg");

    /* Set a specific height */
    height: 50em;

    /* Position and center the image to scale nicely on all screens */
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    position: relative;
}
.hero-text {
    text-align: center;
    line-height: 1.6;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: white;
}
.about {
  padding: 2em;
  margin: 2em auto;
  max-width: 80em;
}
</style>
