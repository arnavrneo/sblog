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

<section class="mb-16 w-full" id="newsletter">
	<div
		class="my-4 w-full border-y border-blue-200 bg-blue-50 p-6 dark:border-gray-600 dark:bg-neutral-800 sm:rounded sm:border-x"
	>
		<div class="flex items-center justify-between space-x-4 text-gray-900 dark:text-gray-100">
			<p class="text-lg font-bold md:text-xl">Something here</p>
		</div>
	</div>
</section>
