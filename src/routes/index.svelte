<script>
	import FeedbackList from '../components/FeedbackList.svelte';

	let feedbacks = [
		{
			id: 1,
			text: 'rsdfsdfsdf jjklhjljh dfgdg lkjljk sdfsfds',
			rating: 7
		},
		{
			id: 2,
			text: 'rsdfsdfsdf cvbcb cbbvcb lkjljk ',
			rating: 5
		},
		{
			id: 3,
			text: 'rsdfsdfsdf sfsbcvbcbdfsdf ljlkjlkj lkjljk sdfscvbcvbcbcbfds',
			rating: 8
		}
	];
</script>

<div class="container mx-auto px-4 ">
	<h1>Welcome to SvelteKit</h1>

	<FeedbackList {feedbacks} />
</div>
