<template>
  <div>
    <h1>{{app_name}}</h1>
    <p>{{ app_dsc() }}</p>
    <proizvodi v-bind:lista_proizvoda="lista_proizvoda" v-bind:neki_objekt="neki_objekt" ulazni_string="Nesto"></proizvodi>
    <proizvodi v-bind:lista_proizvoda="lista_proizvoda" v-bind:neki_objekt="neki_objekt" v-on:button1Clicked="dugmePri"></proizvodi>
    <!--<heder vi-bind:dodatak="dodatakTata"></heder>
    <futer vi-bind:dodatak="dodatakTata"></futer>-->
  </div>
</template>

<script>
import Products from './Products.vue'
import Header from './Header.vue'
import Footer from './Footer.vue'

export default {
  components: {
    'proizvodi': Products,
    'heder': Header,
    'futer': Footer
  },
  data () {
    return {
      app_name: "My Vue App Name",
      dodatakTata: "Dodatak tata...",
      lista_proizvoda: ['Sir', 'Mleko', 'Meso', 'Hleba'],
      neki_objekt:{
        ime: "Vladimir",
        prezime: "Pavković"
      }
    }
  },
  methods:{
    app_dsc(){
      return "My App Description from function"
    },
    dugmePri(eventData){
      console.log("Event capptured");
      console.log(eventData);
    }
  }
}
</script>

<style>

</style>
