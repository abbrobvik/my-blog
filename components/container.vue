<template>
  <div class="container px-4 md:px-0 max-w-6xl mx-auto -mt-32 m-10">
		<div class="mx-0 sm:mx-6 md:mt-20 mt-28">
			<div class="bg-gray-200 w-full text-xl md:text-2xl text-gray-800 leading-normal rounded-t">

				<!--start view-->
				<div class="h-full bg-white rounded overflow-hidden shadow-lg">
					<div class="no-underline hover:no-underline">
            <router-view ></router-view>
					</div>
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
