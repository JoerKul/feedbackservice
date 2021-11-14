<script>
	export let feedbackItem;
</script>

<div class="relative">
	<div class="card lg:card-side bordered my-9 bg-primary-content text-base-200">
		<div class="card-body">
			<h2 class="card-title">No Images</h2>
			<p>{feedbackItem.text}</p>
		</div>
	</div>
	<div
		class="absolute bg-secondary-focus rounded-full w-14 h-14 -left-5 -top-5 ring ring-secondary-focus ring-offset-gray-50 ring-offset-2"
	>
		<p class="text-center pt-4 text-primary-content">{feedbackItem.rating}</p>
	</div>
</div>
