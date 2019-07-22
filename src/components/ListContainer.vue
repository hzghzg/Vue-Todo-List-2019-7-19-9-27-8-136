<template>
  <div id="ListContainer">
    <input type="checkbox" @click="beclicked">{{childData}}
  </div>
</template>

<script>
export default {
  name: 'ListContainer',
  components: {
  },
  methods:{
  },
  props:['childData','listToChild']
}
</script>