<template>
  <div id="app">
    <Header></Header>
    <router-view class="content"/>
    <Footer class="footer"/>
  </div>
</template>
<script>
import { Component, Prop, Vue } from 'vue-property-decorator';
import Header from '@/components/header';
import Footer from '@/components/footer';
@Component({components: {Header, Footer}})
export default class App extends Vue {}
</script>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  min-height: 100vh;
  flex-direction: column;
}

#buttercms {
  height: 40px;
}

p {
  font-size: 1.5em;
  line-height: 1.6;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.content {
  flex: 1;
}
</style>
