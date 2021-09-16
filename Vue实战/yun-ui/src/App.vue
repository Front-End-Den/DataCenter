<template>
  <div>
    <h1 v-big="sum"></h1>
    <button @click="sum++">add one</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      sum:0
    }
  },
  methods: {},
  directives:{
    big(ele,bing){
      ele.innerText = bing.value *10;
    }
  }
}
</script>

<style scope>

</style>
