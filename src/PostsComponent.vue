<template>
    <div>
        <post-component v-for="post in posts" v-bind:post="post"></post-component>
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
        }
    }
</script>