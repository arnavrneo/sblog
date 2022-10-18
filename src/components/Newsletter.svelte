<script>
	let isNewsletterOpen = true;
	function toggleNewsletter() {
		isNewsletterOpen = !isNewsletterOpen;
	}
	function onSubmit() {
		alert(
			'This newsletter section is not yet implemented! if you are seeing this outside of swyxkit then go remind the site author to update Newsletter.svelte.'
		);
	}
</script>
<!-- my-4 w-full border border-blue-200 bg-blue-50 p-6 dark:border-gray-600 dark:bg-neutral-600 sm:rounded sm:border-x -->
<section class="mb-16 w-full" id="newsletter">
	<div
		class="my-4 w-full rounded-xl ring-4 ring-[#a1641d] p-6 dark:bg-[#3C3B3B] ring-4 ring-[#f37c30] sm:rounded sm:border"
	>
		<div class="flex items-center justify-between space-x-4 text-gray-900 dark:text-gray-100">
			<p class="text-lg font-bold md:text-xl">checksomething should be here</p>
		</div>
		{#if isNewsletterOpen}
<!-- 			<form class="relative my-4" on:submit={onSubmit}>
				<input
					type="email"
					aria-label="Email for newsletter"
					placeholder="tim@apple.com"
					autocomplete="email"
					required={true}
					class="mt-1 block w-full rounded-md border-gray-300 bg-white px-4 py-2 pr-32 text-gray-900 focus:border-blue-500 focus:ring-blue-500 dark:bg-gray-800 dark:text-gray-100"
				/><button
					class="absolute right-1 top-1 flex h-8 w-28 items-center justify-center rounded bg-gray-100 px-4 pt-1 font-medium text-gray-900 dark:bg-gray-700 dark:text-gray-100"
					type="submit">Subscribe</button
				>
			</form> -->
<!-- 			<p class="text-sm text-gray-800 dark:text-gray-200">
				3 subscribers including my Mom – <a href="/#newsletter">23 issues</a>
			</p> -->
		{/if}
	</div>
</section>
