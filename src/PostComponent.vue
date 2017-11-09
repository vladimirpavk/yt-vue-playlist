<template>
    <div>
        <h3>{{post.title}}</h3>
        <textarea>{{post.body}}</textarea>
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