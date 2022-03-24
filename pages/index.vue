<template>
  <div class="container px-4 md:px-0 max-w-6xl mx-auto -mt-32 m-10">

			<div class="mx-0 sm:mx-6">

				<!--Nav-->
        <div class="md:h-20 h-28">

        </div>

				<div class="bg-gray-200 w-full text-xl md:text-2xl text-gray-800 leading-normal rounded-t">

				<!--Lead Card-->
				<div class="flex h-full bg-white rounded overflow-hidden shadow-lg">
					<div class="flex flex-wrap no-underline hover:no-underline">
						<div class="w-full md:w-2/3 rounded-t">
							<img src="https://source.unsplash.com/collection/494263/800x600" class="h-full w-full shadow">
						</div>
					</div>
				</div>

      </div>
    </div>
    <div class="md:max-w-screen-xl px-4 py-2 mt-10 mx-auto  container mx-auto">
      <div class="flex flex-wrap justify-center">
        <div @click="goToPost(post.id)" class="md:w-1/4 m-4 md:h-96" v-for="post in posts" :key="post.id">
          <Article :item="post"></Article>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({$content}) {
    let posts = await $content('posts').sortBy('id', 'desc').limit(3).without(['body']).fetch()
    return {
      posts
    }
  },
  methods: {
    goToDish(id) {
      this.$router.push('/post-details/'+id)
    }
  }
}
</script>

<style>

</style>
