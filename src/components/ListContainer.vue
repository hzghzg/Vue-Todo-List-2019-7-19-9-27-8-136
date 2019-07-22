<template>
  <div id="ListContainer">
    <input type="checkbox" @click="beclicked" :checked="childData.status=='BeChosed'" :style="childData.status=='BeChosed'?styleobj:{}" >{{childData.value}}
  </div>
</template>

<script>
export default {
  name: 'ListContainer',
  data(){
    return{
     styleobj:{'text-decoration':"line-through"}
    }
  },
  components: {
  },
  methods:{
    beclicked(){
      this.$emit("childChose",this.childData)
    }
  },
  props:['childData']
}
</script>
<style>
.deletestyle{
  text-decoration: line-through;
}
#ListContainer{
  padding-top:5px;
  padding-left: 5px;
  padding-bottom: 5px; 
}
</style>
}