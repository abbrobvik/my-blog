<template>
<div class=" mx-auto">
    <img :src="post.image"/>
    <h1 class="text-5xl mb-8">{{post.title}}</h1>
    <p class="mb-8">{{post.description}}</p>
    <nuxt-content :document="post"></nuxt-content>
</div>
</template>
<script>
export default {
    async asyncData({$content, params}) {

        let post = await $content('posts/post'+params.id).fetch()
        console.log(post)

        return {
            post
        }
    },
}
</script>
