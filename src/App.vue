<template>
  <div>
    <button v-on:click="promeni_string">Promeni string</button>
  </div>
</template>

<script>

export default {
    data() {
        return {
            neki_string: 'Vladimir Pavković'
        }
    },
    methods: {
        promeni_string(){
            this.neki_string="promenjen string";
        }
    },
    watch:{
        neki_string(){
            console.log('Neki string je promenjen u vrednost: '+this.neki_string);
        }
    }
}
</script>

<style>

</style>