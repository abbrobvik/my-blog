<template>
  <div class="md:max-w-screen-xl px-4 py-2 mt-24 mx-auto  container mx-auto">
    <div class="flex flex-wrap justify-center">
      <div @click="goToPost(post.id)" class="md:w-2/5 m-4 md:h-96" v-for="post in posts" :key="post.id">
        <Article :item="post"></Article>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({$content}) {
    let posts = await $content('posts').without(['body']).fetch()
    return {
      posts
    }
  },
  methods: {
    goToPost(id) {
      this.$router.push('/post-details/'+id)
    }
  }
}
</script>

<style>

</style>
