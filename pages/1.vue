<template>
  <div class="md:max-w-screen-xl px-4 py-2 mt-24 mx-auto  container mx-auto">
    <div class="flex flex-wrap justify-center">
      <div @click="goToDish(dish.id)" class="md:w-2/5 m-4 md:h-96" v-for="dish in dishes" :key="dish.id">
        <DishListItem :item="dish"></DishListItem>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  async asyncData({$content}) {
    let dishes = await $content('dishes').without(['body']).fetch()
    return {
      dishes
    }
  },
  methods: {
    goToDish(id) {
      this.$router.push('/dish-details/'+id)
    }
  }
}
</script>
