<template>
  <div>
    <h1>Header {{changed}}</h1>
  </div>
</template>

<script>
export default {
  data() {
    changed: 'not changed';
  },
  methods:{
    changeTitle(){
      this.changed="is changed";
    }
  }
}
</script>

<style>

</style>
