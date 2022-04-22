<template>
  <div class="container px-4 md:px-0 max-w-6xl mx-auto -mt-32 m-10">
		<div class="mx-0 sm:mx-6 md:mt-20 mt-28">
			<div class="bg-gray-200 w-full text-xl md:text-2xl text-gray-800 leading-normal rounded-t">

				<!--start view-->
				<div class="h-full bg-white rounded overflow-hidden shadow-lg">
					<div class="no-underline hover:no-underline">
						<div class="w-full rounded-t">
							<img src="/why.png" class="bild md:h-52 w-full object-cover p-4 rounded-3xl">
						</div>
            <div class="flex flex-wrap justify-center">
              <div class="h-0.5 w-full mx-4 mt-4 rounded-md" style="background-color: #f1f1f1;"></div>
              <div class="w-full md:w-2/3 mx-4">
                <h1 class="mt-8 font-serif flex flex-wrap justify-center ">Some questions</h1>
                <p class="text-base my-4"><nuxt-content :document="faq"/></p>
              </div>
            </div>
					</div>
				</div>
      </div>
    </div>
  </div>
</template>

<script>
export default{
    async asyncData({ $content }) {
        let faq = await $content("faq").fetch();
        return {
            faq
        };
    }
}
</script>

<style>
h2{
  font-family: ui-serif, Georgia, "Times New Roman", Times, serif;
  font-size: 1.25rem;
  line-height: 1.75rem;
}
p{
  font-family: 'Segeo UI';
  font-size: 1rem;
  line-height: 1.5rem;
}
</style>
