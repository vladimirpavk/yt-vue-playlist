<template>
  <div>
    <my_header></my_header>
    <my_footer></my_footer>
  </div>
</template>

<script>
import Header from './Header.vue';
import Footer from './Footer.vue';

export default {
    components:{
        'my_header': Header,
        'my_footer': Footer
    }
}
</script>

<style>

</style>