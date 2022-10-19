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
		class="my-4 w-full rounded-xl ring-4 ring-[#a1641d] p-6 dark:ring-4 ring-[#f37c30] sm:rounded-xl sm:border"
	>
		<div class="flex items-center justify-between space-x-4 text-gray-900 dark:text-gray-100">
			<p class="text-lg font-bold md:text-xl">Want to contribute?</p>
			<button
				aria-label="Toggle CTA"
				class="flex h-9 w-9  items-center justify-center rounded-lg ring-gray-300 transition-all hover:ring-2"
				on:click={toggleNewsletter}
			>
				{#if isNewsletterOpen}
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-5 w-5"
						viewBox="0 0 20 20"
						fill="currentColor"
					>
						<path
							fill-rule="evenodd"
							d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
							clip-rule="evenodd"
						/>
					</svg>
				{:else}
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-5 w-5"
						viewBox="0 0 20 20"
						fill="currentColor"
					>
						<path
							fill-rule="evenodd"
							d="M15.707 4.293a1 1 0 010 1.414l-5 5a1 1 0 01-1.414 0l-5-5a1 1 0 011.414-1.414L10 8.586l4.293-4.293a1 1 0 011.414 0zm0 6a1 1 0 010 1.414l-5 5a1 1 0 01-1.414 0l-5-5a1 1 0 111.414-1.414L10 14.586l4.293-4.293a1 1 0 011.414 0z"
							clip-rule="evenodd"
						/>
					</svg>
				{/if}
			</button>
		</div>
		{#if isNewsletterOpen}
			<form class="relative my-4" on:submit={onSubmit}>
				<div
					class="items-center justify-center rounded px-4 pt-1 font-medium text-gray-900 dark:text-gray-100"
					type="submit">
					<ul>
						<li>Check out our <a class="p-1 text-gray-800 transition-all hover:ring-orange-400 dark:text-gray-200 dark:hover:ring-orange-400 sm:px-3 sm:py-2 md:inline-block" href="https://github.com/arnavrneo/sblog">Github</a> about the process!</li>
						<li>Can be something else here.</li>
					</ul>
					 </div>
			</form>
<!-- 			<p class="text-sm text-gray-800 dark:text-gray-200">
				3 subscribers including my Mom – <a href="/#newsletter">23 issues</a>
			</p> -->
		{/if}
	</div>
</section>
