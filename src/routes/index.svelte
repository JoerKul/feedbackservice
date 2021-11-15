<script>
	import FeedbackStats from '../Components/FeedbackStats.svelte';
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
			rating: 4
		},
		{
			id: 3,
			text: 'rsdfsdfsdf sfsbcvbcbdfsdf ljlkjlkj lkjljk sdfscvbcvbcbcbfds',
			rating: 6
		},
		{
			id: 4,
			text: 'loremd dkowmfwpovüioen oiefnaöeionfpewoinf eöoifnöeiowafnöaewifn',
			rating: 8
		}
	];

	$: sum = feedbacks.reduce((a, { rating }) => a + rating, 0);
	$: avg = sum / feedbacks.length || 0;
	$: count = feedbacks.length;
</script>

<div class="container mx-auto px-6 sm:px-4 ">
	<h1 class="sm:text-5xl text-4xl">Welcome</h1>

	<FeedbackStats {avg} {count} />
	<FeedbackList {feedbacks} />
</div>
