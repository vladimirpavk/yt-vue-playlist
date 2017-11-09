<template>
  <div>
    <component v-bind:is="cur_component"></component>
    <button v-on:click="button1Clicked">Change current component</button>
    <hr>

    <label for="checkBox1">Vrednost 1</label>
    <input type="checkbox" value="Vrednost1" id="checkBox1" v-model="checkBoxValues"/>

    <label for="checkBox2">Vrednost 2</label>
    <input type="checkbox" value="Vrednost2" id="checkBox2" v-model="checkBoxValues"/>

    <label for="checkBox1">Vrednost 3</label>
    <input type="checkbox" value="Vrednost3" id="checkBox3" v-model="checkBoxValues"/>

    <hr>

    {{checkBoxValues}}
    
    <hr>

    <button v-on:click="getPosts">Get Posts</button>

    <posts-component v-bind:posts="this.postsArray"></posts-component>
    
  </div>
</template>

<script>
import Header from './Header.vue';
import Footer from './Footer.vue';
import PostsComponent from './PostsComponent.vue';

export default {
    components:{
        'my_header': Header,
        'my_footer': Footer,
        'posts-component': PostsComponent
    },
    data(){
      return{
        cur_component: 'my_header',
        checkBoxValues: [],
        postsArray: []
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
      },
      getPosts(){
        this.$http.get('https://jsonplaceholder.typicode.com/posts').then((data)=>{
          //console.log(data);
          this.postsArray=data.body;
          //console.log(this.postsArray);
        }).catch((error)=>{
          console.log(error)
        })
      }
    }

}
</script>

<style>

</style>