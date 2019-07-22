<template>
  <div id="Body">
      <InputBar @fetchChildValue="parentFetchChildValue"></InputBar>
      <ListContainer v-for="item in List" :key="item" :childData="item.value" :listToChild="List"></ListContainer>
  </div>
</template>

<script>
import InputBar from "../components/InputBar.vue";
import ListContainer from "../components/ListContainer.vue";
export default {
  name: 'Body',
  data(){
      return{
          List:[{status:"Notchosed",value:"123"},{status:"Notchosed",value:"456"},{status:"Notchosed",value:"789"},{status:"Notchosed",value:"1011"}]
      }
  },
  methods:{
    parentFetchChildValue(data){
        this.List.push(data)
    }
  }
  ,
  components: {
      InputBar,
      ListContainer
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