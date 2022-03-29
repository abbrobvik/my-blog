<template>
<div class="m-3">
<div class="mx-auto md:w-2/3">

    <!-- post - image -->

     <div class="container px-4 md:px-0 max-w-6xl mx-auto -mt-32 m-10">

				<!--post image-->
				<div class="flex h-full bg-white rounded overflow-hidden shadow-lg md:mt-20 mt-28">
					<div class="flex h-full bg-white rounded overflow-hidden shadow-lg">
			      <div class="flex flex-wrap no-underline hover:no-underline">
			        <img :src="post.image" class="bild h-52 w-full object-cover " >
			      </div>
		      </div>
				</div>
    </div>



    <h1 class="text-5xl mb-8">{{post.title}}</h1>
    <p class="mb-8">{{post.description}}</p>
    <nuxt-content :document="post"></nuxt-content>
</div>
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
