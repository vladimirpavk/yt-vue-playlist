<template>
  <div>
    <h1 v-on:click="footerClicked">Futer</h1>
  </div>
</template>

<script>
import { eventBus } from './main.js';

export default {
  methods:{
    footerClicked(){
      console.log('footerClicked');
      eventBus.$emit('footerClickedEvenet', {
        name1: 'Neki podataka',
        value1: 'Neka vrednost'
      });
    }
  }
}
</script>

<style>

</style>