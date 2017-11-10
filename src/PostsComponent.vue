<template>
    <div>
    <input v-model="search" placeholder="Search for posts..." />
    <!-- <p>{{ search }}</p> -->
    <p> {{computedSearch }} </p>
    <!-- <post-component v-for="post in posts" v-bind:post="post"></post-component> -->
    <post-component v-for="post in computedPosts" v-bind:post="post"></post-component>
    </div>
</template>
<script>
import PostComponent from './PostComponent.vue';

    export default{
        components: {
            'post-component': PostComponent
        },
        props:{
            posts: {
                type: Array,
                required: true
            }
        },
        created(){
            //console.log(post);
        },
        data() {
            return {
                search: ''
            }
        },
        computed:{
            computedSearch(){
                return this.search.slice(1,5);
            },
            computedPosts(){
                return this.posts.filter((element)=>{return element.title.match(this.search)});
            }
        }
    }
</script>