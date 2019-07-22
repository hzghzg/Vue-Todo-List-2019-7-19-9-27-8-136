<template>
  <div id="Body">
      <InputBar id="input" @fetchChildValue="parentFetchChildValue"></InputBar>
      <ListContainer  v-for="item in List" :key="item.value" :childData="item" @childChose="changeStatus"></ListContainer>
  </div>
</template>

<script>
import InputBar from "../components/InputBar.vue";
import ListContainer from "../components/ListContainer.vue";
export default {
  name: 'Body',
  data(){
      return{
          List:[{status:"Notchosed",value:"123"},{status:"Notchosed",value:"456"},{status:"Notchosed",value:"789"},{status:"Notchosed",value:"1011"}],
          reservedList:[{status:"Notchosed",value:"123"},{status:"Notchosed",value:"456"},{status:"Notchosed",value:"789"},{status:"Notchosed",value:"1011"}]
      }
  },
  methods:{
    parentFetchChildValue(data){
        let obj={status:"Notchosed",value:data};
        this.List.push(obj);
        this.reservedList.push(obj);
    },
    changeStatus(v){
        let index=this.List.map(item=>item.value).indexOf(v.value);
        if(this.List[index].status=="Notchosed"){
            this.List[index].status="BeChosed";
            this.reservedList[index].status="BeChosed";
        }
        else{
            this.List[index].status="Notchosed";
            this.reservedList[index].status="Notchosed";
        }
    },
    displayList(completeStatus){
        this.List=this.reservedList;
        if(completeStatus=="active")
        this.List=this.List.filter(item=>item.status=="Notchosed")
        else if(completeStatus=="complete")
        this.List=this.List.filter(item=>item.status=="BeChosed")
        else
        this.List=this.List;
    }
  }
  ,
  components: {
      InputBar,
      ListContainer
  },
  props:['']
}
</script>

<style>
#input{
    margin-bottom:40px;
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