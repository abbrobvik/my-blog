<template>
  <div class="m-3">
    <div class="container px-4 md:px-0 max-w-6xl mx-auto -mt-32 m-10">
		  <div class="mx-0 sm:mx-6 md:mt-20 mt-28">
			  <div class="bg-gray-200 w-full text-xl md:text-2xl text-gray-800 leading-normal rounded-t">
				  <div class="h-full bg-white rounded overflow-hidden shadow-lg">
					  <div class="no-underline hover:no-underline">
              <!-- Bild för post -->
						  <div class="w-full rounded-t">
							  <img :src="post.image" class="bild md:h-52 h-32 w-full object-cover" >
						  </div>
              <!-- Text för post -->
              <div class="flex justify-center">
                <div class="w-full md:w-2/3 mx-4">
                  <h1 class="mt-8 font-serif flex flex-wrap justify-center m-4">{{post.title}}</h1>
                  <p class="font-sans text-base m-4">{{post.description}}</p>
                  <nuxt-content :document="post" class="m-4 font-sans text-base"></nuxt-content>
                </div>
              </div>
					  </div>
				  </div>
        </div>
      </div>
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
