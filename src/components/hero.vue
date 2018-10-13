<template>
  <div role="img" :aria-label="alt" :style="`background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('${imagelocation}');`" class="hero-image md-elevation-12">
    <div class="hero-text">
      <h1>{{ text }}</h1>
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class HeroImage extends Vue {
  @Prop() private imagelocation!: string;
  @Prop() private text!: string;
  @Prop() private alt!: string;
}
</script>
<style scoped>
.hero-image {
    /* Use "linear-gradient" to add a darken background effect to the image (photographer.jpg). This will make the text easier to read */
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
</style>
