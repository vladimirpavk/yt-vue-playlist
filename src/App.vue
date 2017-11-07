<template>
  <div>
    <component v-bind:is="cur_component"></component>
    <button v-on:click="button1Clicked">Change current component</button>
  </div>
</template>

<script>
import Header from './Header.vue';
import Footer from './Footer.vue';

export default {
    components:{
        'my_header': Header,
        'my_footer': Footer
    },
    data(){
      return{
        cur_component: 'my_header'
      }
    },
    methods:{
      button1Clicked(){
        if(this.cur_component == 'my_header'){
          this.cur_component = 'my_footer'
        }
        else
        {
          this.cur_component = 'my_header'
        }
      }
    }

}
</script>

<style>

</style>