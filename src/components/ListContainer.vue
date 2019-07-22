<template>
  <div id="ListContainer">
    <input type="checkbox" @click="beclicked" :checked="childData.status=='BeChosed'">{{childData.value}}
  </div>
</template>

<script>
export default {
  name: 'ListContainer',
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