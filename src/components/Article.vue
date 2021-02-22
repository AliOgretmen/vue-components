<template>
    <div>
        <h2>Article component</h2>
        <h3> {{ title}}</h3>
        <h3 v-bind="$attrs"> Likes - {{likes}}</h3>
        <h3> Pulished?  {{isPublished ? 'Yes' : 'No'}}</h3>

    </div>
</template>

<script>
    export default {
        name: 'Article',
        props:{
            title:{
                type: String,
                required: true,
                default: 'Article is required'
            },
            likes: Number,
            isPublished: Boolean,
        },
        inheritAttrs: false,
        
    }
</script>

<style >

</style>