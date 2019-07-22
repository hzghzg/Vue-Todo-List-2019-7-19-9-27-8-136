<template>
  <div id="Footer">
      <a href="" @click="displayAll">ALL</a>
      <a href="" @click="displayActive">Active</a>
      <a href="" @click="displayComplete">Complete</a>
  </div>
</template>

<script>

export default {
  name: 'Footer',
  components: {
  }
}
</script>

<style>
a{
    display: inline-block;
    margin:10px;
    color: #FFB5B5;
    text-decoration:none;

}
.buttonstyle{
    color:indianred;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>