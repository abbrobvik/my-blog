<template>
  <div class="container px-4 md:px-0 max-w-6xl mx-auto -mt-32 m-10">
		<div class="mx-0 sm:mx-6 md:mt-20 mt-28">
			<div class="bg-gray-200 w-full text-xl md:text-2xl text-gray-800 leading-normal rounded-t">

				<!--start view-->
				<div class="h-full bg-white rounded overflow-hidden shadow-lg">
					<div class="no-underline hover:no-underline">
						<div class="w-full rounded-t">
							<img :src="randomImage" class="bild md:h-52 h-32 w-full object-cover">
						</div>
            <div class="flex justify-center">
              <div class="w-full md:w-1/2 mx-4">
                <h1 class="mt-8 font-serif flex flex-wrap justify-center ">{{Welcome.title}}</h1>
                <p class="font-sans text-base my-4">{{Welcome.description}}</p>
              </div>
            </div>
					</div>
				</div>
      </div>
    </div>

    <!-- Newest-post -->
    <div class="flex flex-wrap justify-center ">
      <div class="md:mt-10 mt-4 py-4 md:px-96 px-4 rounded overflow-hidden shadow-lg" style="background-color: #f1f1f1;">
        <h1 class="font-serif text-xl">Newest posts - down below </h1>
      </div>
    </div>

    <!-- three newest posts -->
    <div class="md:max-w-screen-xl px-4 py-2 mt-4 mx-auto  container">
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
    async asyncData({ $content }) {
        let posts = await $content("posts").sortBy("id", "desc").limit(3).without(["body"]).fetch();
        let Welcome = await $content("Welcome").sortBy("id").without(["body"]).fetch();
        return {
            posts,
            Welcome
        };
    },
    data() {
        return {
            random: Math.round(19 * Math.random())
        };
    },
    computed: {
        randomImage() {
            return `Bilder-blogg/Bild${this.random}.png`;
        }
    },
    methods: {
        goToPost(id) {
            this.$router.push("/post/" + id);
        }
    }
}
</script>

<style>
  .bild{
    height: 500px;
    width: 100%;
  }

</style>
