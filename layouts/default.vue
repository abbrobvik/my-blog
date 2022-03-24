<template>
  <div>
    <Header/>
    <nuxt/>
    <Fotter/>
  </div>
</template>

<script>
import Header from "../components/Header.vue"
import Fotter from "../components/Fotter.vue"

export default {
    components: { Header, Fotter }
}
</script>

<style>
</style>
