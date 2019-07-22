<template>
  <div id="InputBar">
      <label><input type="text" class="inputstyle" v-model="text"></label>
      <input type="button" value="Add" class="buttonclass" @click="parentTrigger" @keypress.enter="parentTrigger">
  </div>
</template>

<script>
export default {
  name: 'InputBar',
  data(){
      return{
          text:""
      }
  },
  methods:{
      parentTrigger(){
          this.$emit('fetchChildValue',this.text)
          this.text=""
      }

  },
  components: {
  }
}
</script>
<style>
.inputstyle{
    width:300px;
    margin-right:10px 
}
.buttonclass{
    background-color: #F08080;
    color:ghostwhite;
    border-radius: 5px;
    border:0px;
}
</style>