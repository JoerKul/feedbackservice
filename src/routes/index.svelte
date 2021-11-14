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

	$: count = feedbacks.length;
	let avg = 'to be defined';
</script>

<div class="container mx-auto px-4 ">
	<h1 class="text-5xl">Welcome</h1>
	<div class="flex justify-between text-2xl mt-6 mb-16">
		<div>{count} Reviews</div>
		<div>Average Rating: {avg}</div>
	</div>
	<FeedbackList {feedbacks} />
</div>
