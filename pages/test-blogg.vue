<template>
<div>
  <div class="max-w-screen-xl px-4 py-2 mt-24 mx-auto border-2 container mx-auto">
    <div class="flex flex-wrap justify-center">
      <div @click="goToDish(dish.id)" class="w-80 m-4" v-for="dish in dishes" :key="dish.id">
        <DishListItem :item="dish"></DishListItem>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {

}
</script>

<style>

</style>
