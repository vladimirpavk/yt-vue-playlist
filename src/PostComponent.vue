<template>
    <div>
        <h3>{{post.title}}</h3>
        <article>{{post.body}}</article>
    </div>
</template>
<script>
    export default{
        props:{
            post: {
                type: Object,
                required: true
            }
        }
    }
</script>