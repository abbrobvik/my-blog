<template>
  <div  class="py-4 text-center px-2 sans-serif text-base leading-6 bg-white flex-1 bg-white rounded-t rounded-b-none overflow-hidden shadow-lg h-96">
    <div  class="px-4 flex flex-wrap justify-center">
        <img :src="item.image" alt="dish image" class="h-52 w-full object-cover" >
        <h3 class="font-serif text-xl">{{item.title}}</h3>
        <p class="font-sans text-base">{{item.description}}</p>
    </div>
  </div>
</template>

<script>
export default {
    props:['item'],
    data() {
        return {

        }
    }
}
</script>
