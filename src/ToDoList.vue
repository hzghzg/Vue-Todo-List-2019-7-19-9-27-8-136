<template>
  <div id="app">
    <Header></Header>
    <Body ref="body"></Body>
    <Footer @childStatus="getFooterStatus"></Footer>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Body from "./components/Body.vue";
import Footer from "./components/Footer.vue";

export default {
  name: 'app',
  methods:{
    getFooterStatus(f){
      this.$refs.body.displayList(f);
    }
  },
  components: {
    Header,
    Body,
    Footer
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
