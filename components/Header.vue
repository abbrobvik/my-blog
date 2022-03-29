<template>
  <div>
    <NavBar/>
    <div class=" h-32 md:h-60 lg:h-96">
      <div class="hero-image flex wrap justify-center items-center h-32 md:h-60  lg:h-96 rounded-b-none shadow-lg overflow-hidden rounded-t flex-1">
        <h1 class="font-serif md:text-5xl sm:text-base text-white">
          <a href="/">Robins - Blogg</a>
          </h1>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.hero-image {
  background-image: url("/Header-background.jpg"); /* The image used */
  width: 100%;
  background-color: #2e2c2c; /* Used if the image is unavailable */
  background-position: center; /* Center the image */
  background-repeat: no-repeat; /* Do not repeat the image */
  background-size: cover; /* Resize the background image to cover the entire container */
}
</style>
