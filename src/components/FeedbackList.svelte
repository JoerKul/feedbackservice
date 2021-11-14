<script>
	import FeedbackItem from './FeedbackItem.svelte';

	export let feedbacks;
</script>

{#each feedbacks as feedbackItem}
	<FeedbackItem {feedbackItem} />
{/each}
