<script>
	import RangeSlider from 'svelte-range-slider-pips';

	import FeedbackForm from '../components/FeedbackForm.svelte';
	import FeedbackStats from '../components/FeedbackStats.svelte';
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
		},
		{
			id: 5,
			text: 'rsdfsdfsdf jjklhjljh dfgdg lkjljk sdfsfds',
			rating: 5
		},
		{
			id: 6,
			text: 'rsdfsdfsdf cvbcb cbbvcb lkjljk ',
			rating: 4
		},
		{
			id: 7,
			text: 'rsdfsdfsdf sfsbcvbcbdfsdf ljlkjlkj lkjljk sdfscvbcvbcbcbfds',
			rating: 9
		},
		{
			id: 8,
			text: 'loremd dkowmfwpovüioen oiefnaöeionfpewoinf eöoifnöeiowafnöaewifn',
			rating: 8
		}
	];

	let hue = [360];
	$: lightColor = `hsl(${Math.round(hue[0] - 10)}, 66%, 51%)`;
	$: color = `hsl(${Math.round(hue[0])}, 66%, 54%)`;
	$: formatedHue = Math.round(hue / 10);

	$: showMenu = true;
</script>

<!-- <div class="container mx-auto px-6 sm:px-4">
	// <h1 class="text-5xl font-bold text-primary">Welcome</h1> 

	<FeedbackForm />
	<FeedbackStats {avg} {count} />
	<FeedbackList {feedbacks} />
</div> -->

<section class="w-full px-3 antialiased bg-indigo-600 lg:px-6">
	<div class="mx-auto max-w-7xl">
		<nav class="flex items-center w-full h-24 select-none">
			<div
				class="relative flex flex-wrap items-center justify-between w-full h-24 mx-auto font-medium md:justify-center"
			>
				<a href="#_" class="w-1/4 py-4 pl-6 pr-4 md:pl-4 md:py-0">
					<span class="p-1 text-xl font-black leading-none text-white select-none"
						><span>AXperimentalists</span><span class="text-indigo-300">.</span></span
					>
				</a>
				<div
					class="fixed top-0 left-0 z-40 items-center hidden w-full h-full p-3 text-xl bg-gray-900 bg-opacity-50 md:text-sm lg:text-base md:w-3/4 md:bg-transparent md:p-0 md:relative md:flex"
					class:hidden={showMenu}
				>
					<div
						class="flex-col w-full  h-full overflow-hidden bg-white rounded-lg select-none md:bg-transparent md:rounded-none md:relative md:flex md:flex-row md:overflow-auto"
					>
						<div
							class="flex flex-col items-center justify-center w-full h-full mt-12 text-center text-indigo-700 md:text-indigo-200 md:w-2/3 md:mt-0 md:flex-row md:items-center"
						>
							<a
								href="/"
								class="inline-block px-4 py-2 mx-2 font-medium text-left text-indigo-700 md:text-white md:px-0 lg:mx-3 md:text-center"
								>Home</a
							>
							<a
								href="/"
								class="inline-block px-4 py-2 mx-2 font-medium text-left md:px-0 hover:text-indigo-800 md:hover:text-white lg:mx-3 md:text-center"
								>Features</a
							>
							<a
								href="/"
								class="inline-block  px-4 py-2 mx-2 font-medium text-left md:px-0 hover:text-indigo-800 md:hover:text-white lg:mx-3 md:text-center"
								>Blog</a
							>
							<a
								href="/"
								class="inline-block  px-4 py-2 mx-2 font-medium text-left md:px-0 hover:text-indigo-800 md:hover:text-white lg:mx-3 md:text-center"
								>Contact</a
							>
						</div>
						<div
							class="flex flex-col items-center justify-end w-full h-full pt-4 md:w-1/3 md:flex-row md:py-0"
						>
							<a
								href="#_"
								class="w-full pl-6 mr-0 text-indigo-200 hover:text-white md:pl-0 md:mr-3 lg:mr-5 md:w-auto"
								>Sign In</a
							>
							<a
								href="#_"
								class="inline-flex items-center justify-center px-4 py-2 mr-1 text-base font-medium leading-6 text-indigo-600 whitespace-no-wrap transition duration-150 ease-in-out bg-white border border-transparent rounded-full hover:bg-white focus:outline-none focus:border-indigo-700 focus:shadow-outline-indigo active:bg-indigo-700"
								>Sign Up</a
							>
						</div>
					</div>
				</div>
				<div
					on:click={() => (showMenu = !showMenu)}
					class="absolute right-0 z-50 flex flex-col items-end w-10 h-10 p-2 mr-4 rounded-full cursor-pointer md:hidden hover:bg-gray-900 hover:bg-opacity-10 text-gray-100"
				>
					<svg
						class="w-6 h-6"
						fill="none"
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						viewBox="0 0 24 24"
						stroke="currentColor"
						class:hidden={!showMenu}
					>
						<path d="M4 6h16M4 12h16M4 18h16" />
					</svg>
					<svg
						class="w-6 h-6"
						fill="none"
						stroke="currentColor"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
						style="display: none;"
						class:hidden={showMenu}
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M6 18L18 6M6 6l12 12"
						/>
					</svg>
				</div>
			</div>
		</nav>
		<div class="container py-32 mx-auto text-center sm:px-4">
			<h1
				class="text-4xl font-extrabold leading-10 tracking-tight text-white sm:text-5xl sm:leading-none md:text-6xl xl:text-7xl"
			>
				<span class="block">How would you rate your</span>
				<span class="relative inline-block mt-3  text-white">products we build</span>
			</h1>

			<div class="mx-auto mt-20 w-10/12">
				<div style="--range-handle-focus: {color}; --range-range: {lightColor}">
					<RangeSlider
						id="color-pips"
						bind:values={hue}
						range="min"
						min={10}
						max={100}
						pipstep={10}
						pips
						first={false}
						last={false}
					/>
				</div>

				<div class="stat-value text-indigo-100 text-6xl">{formatedHue}</div>

				<div
					class="max-w-lg mx-auto mt-6 text-sm text-center text-indigo-200 md:mt-12 sm:text-base md:max-w-xl md:text-lg xl:text-xl"
				>
					If you're ready to change the way you've been automating, use to make it fun and easy!
				</div>
				<div
					class="relative flex items-center max-w-md mx-auto mt-12 overflow-hidden text-center rounded-full"
					data-dashlane-rid="bd17d1ca3a893f28"
					data-form-type="other"
				>
					<input
						type="text"
						name="email"
						placeholder="Tell us something that keeps you comming back"
						class="w-full h-12 px-6 py-2 font-medium text-indigo-800 focus:outline-none"
						data-dashlane-rid="8abe8cc49d2b073b"
						data-kwimpalastatus="alive"
						data-kwimpalaid="1638214167818-1"
						data-form-type="email"
					/>
					<span class="relative top-0 right-0 block">
						<button
							type="button"
							class="inline-flex items-center w-32 h-12 px-8 text-base font-bold leading-6 text-white transition duration-150 ease-in-out bg-indigo-400 border border-transparent hover:bg-indigo-700 focus:outline-none active:bg-indigo-700"
							data-dashlane-rid="71b0fd74b18191db"
							data-dashlane-label="true"
							data-form-type="action"
						>
							Sign Up
						</button>
					</span>
				</div>
				<div class="mt-8 text-sm text-indigo-300">
					By signing up, you agree to our terms and services.
				</div>
			</div>
		</div>
	</div>
</section>

<!-- Section 2 -->
<section class="flex items-center justify-center py-16 bg-gray-100 min-w-screen">
	<div class="max-w-6xl px-12 mx-auto bg-gray-100 md:px-16 xl:px-10">
		<div class="flex flex-col lg:flex-row justify-between">
			<div
				class="flex flex-col items-start justify-center w-full h-full pr-8 mb-10 lg:mb-8 lg:w-1/2 lg:ml-6"
			>
				<p class="mb-2 text-base font-medium tracking-tight text-indigo-500 uppercase">
					Our customers love our product
				</p>
				<h2
					class="text-4xl font-extrabold leading-10 tracking-tight text-gray-900 sm:text-5xl sm:leading-none md:text-6xl lg:text-5xl xl:text-6xl"
				>
					Testimonials
				</h2>
				<p class="my-6 text-lg text-gray-600">
					Don't just take our word for it, read from our extensive list of case studies and customer
					testimonials.
				</p>
				<a
					href="#_"
					class="flex items-center justify-center px-8 py-3 text-base font-medium leading-6 text-white transition duration-150 ease-in-out bg-indigo-600 border border-transparent rounded-md shadow hover:bg-indigo-500 focus:outline-none focus:border-indigo-700 focus:shadow-outline-indigo md:py-4 md:text-lg md:px-10"
					>View Case Studies</a
				>
			</div>
			<div
				class="flex flex-col items-center justify-between col-span-6 px-8 py-12 space-y-4  bg-white rounded-lg shadow"
			>
				<div class="p-3 text-white bg-blue-500 rounded-full">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="w-8 h-8 "
						viewBox="0 0 24 24"
						stroke-width="1.5"
						stroke="currentColor"
						fill="none"
						stroke-linecap="round"
						stroke-linejoin="round"
					>
						<path stroke="none" d="M0 0h24v24H0z" fill="none" />
						<path d="M14 3v4a1 1 0 0 0 1 1h4" />
						<path d="M5 8v-3a2 2 0 0 1 2 -2h7l5 5v11a2 2 0 0 1 -2 2h-5" />
						<circle cx="6" cy="14" r="3" />
						<path d="M4.5 17l-1.5 5l3 -1.5l3 1.5l-1.5 -5" />
					</svg>
				</div>
				<h4 class="text-xl font-medium text-gray-700">Certifications</h4>
				<p class="text-base text-center text-gray-500">
					Each of our plan will provide you and your team with certifications.
				</p>
			</div>
		</div>

		<div class="flex flex-col items-center lg:flex-row">
			<div class="w-full lg:w-1/2 my-6 lg:mx-6">
				<blockquote
					class="flex items-center justify-between w-full col-span-1 p-6 bg-white rounded-lg shadow"
				>
					<div class="flex flex-col pr-8">
						<div class="relative pl-12">
							<svg
								class="absolute left-0 w-10 h-10 text-indigo-500 fill-current"
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 100 125"
							>
								<path
									d="M30.7 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2C12.7 83.1 5 72.6 5 61.5c0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S30.7 31.6 30.7 42zM82.4 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2-11.8 0-19.5-10.5-19.5-21.6 0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S82.4 31.6 82.4 42z"
								/>
							</svg>
							<p class="mt-2 text-sm text-gray-600 sm:text-base lg:text-sm xl:text-base">
								Awesome product! And the customer service is exceptionally well.
							</p>
						</div>

						<h3
							class="pl-12 mt-3 text-sm font-medium leading-5 text-gray-800 truncate sm:text-base lg:text-sm"
						>
							Jane Cooper
							<span class="mt-1 text-sm leading-5 text-gray-500 truncate">- CEO SomeCompany</span>
						</h3>
					</div>
					<img
						class="flex-shrink-0 w-20 h-20 bg-gray-300 rounded-full xl:w-24 xl:h-24"
						src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&amp;ixid=eyJhcHBfaWQiOjEyMDd9&amp;auto=format&amp;fit=facearea&amp;facepad=4&amp;w=256&amp;h=256&amp;q=60"
						alt=""
					/>
				</blockquote>
				<blockquote
					class="flex items-center justify-between w-full col-span-1 p-6 mt-4 bg-white rounded-lg shadow"
				>
					<div class="flex flex-col pr-10">
						<div class="relative pl-12">
							<svg
								class="absolute left-0 w-10 h-10 text-indigo-500 fill-current"
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 100 125"
							>
								<path
									d="M30.7 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2C12.7 83.1 5 72.6 5 61.5c0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S30.7 31.6 30.7 42zM82.4 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2-11.8 0-19.5-10.5-19.5-21.6 0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S82.4 31.6 82.4 42z"
								/>
							</svg>
							<p class="mt-2 text-sm text-gray-600 sm:text-base lg:text-sm xl:text-base">
								I can't express enough, how amazing this service has been for my company.
							</p>
						</div>
						<h3
							class="pl-12 mt-3 text-sm font-medium leading-5 text-gray-800 truncate sm:text-base lg:text-sm "
						>
							John Doe
							<span class="mt-1 text-sm leading-5 text-gray-500 truncate">- CEO SomeCompany</span>
						</h3>
						<p class="mt-1 text-sm leading-5 text-gray-500 truncate" />
					</div>
					<img
						class="flex-shrink-0 w-24 h-24 bg-gray-300 rounded-full"
						src="https://images.unsplash.com/photo-1527980965255-d3b416303d12?ixlib=rb-1.2.1&amp;ixid=eyJhcHBfaWQiOjEyMDd9&amp;aauto=format&amp;fit=facearea&amp;facepad=4&amp;w=256&amp;h=256&amp;q=60"
						alt=""
					/>
				</blockquote>
				<blockquote
					class="flex items-center justify-between w-full col-span-1 p-6 mt-4 bg-white rounded-lg shadow"
				>
					<div class="flex flex-col pr-10">
						<div class="relative pl-12">
							<svg
								class="absolute left-0 w-10 h-10 text-indigo-500 fill-current"
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 100 125"
							>
								<path
									d="M30.7 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2C12.7 83.1 5 72.6 5 61.5c0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S30.7 31.6 30.7 42zM82.4 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2-11.8 0-19.5-10.5-19.5-21.6 0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S82.4 31.6 82.4 42z"
								/>
							</svg>
							<p class="mt-2 text-sm text-gray-600 sm:text-base lg:text-sm xl:text-base">
								I can't express enough, how amazing this service has been for my company.
							</p>
						</div>

						<h3
							class="pl-12 mt-3 text-sm font-medium leading-5 text-gray-800 truncate sm:text-base lg:text-sm "
						>
							John Smith
							<span class="mt-1 text-sm leading-5 text-gray-500 truncate">- CEO SomeCompany</span>
						</h3>
						<p class="mt-1 text-sm leading-5 text-gray-500 truncate" />
					</div>
					<img
						class="flex-shrink-0 w-24 h-24 bg-gray-300 rounded-full"
						src="https://images.unsplash.com/photo-1545167622-3a6ac756afa4?ixlib=rrb-1.2.1&amp;ixid=eyJhcHBfaWQiOjEyMDd9&amp;aauto=format&amp;fit=facearea&amp;facepad=4&amp;w=256&amp;h=256&amp;q=60"
						alt=""
					/>
				</blockquote>
			</div>

			<div class="w-full lg:w-1/2">
				<blockquote
					class="flex items-center justify-between w-full col-span-1 p-6 bg-white rounded-lg shadow"
				>
					<div class="flex flex-col pr-8">
						<div class="relative pl-12">
							<svg
								class="absolute left-0 w-10 h-10 text-indigo-500 fill-current"
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 100 125"
							>
								<path
									d="M30.7 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2C12.7 83.1 5 72.6 5 61.5c0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S30.7 31.6 30.7 42zM82.4 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2-11.8 0-19.5-10.5-19.5-21.6 0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S82.4 31.6 82.4 42z"
								/>
							</svg>
							<p class="mt-2 text-sm text-gray-600 sm:text-base lg:text-sm xl:text-base">
								Awesome product! And the customer service is exceptionally well.
							</p>
						</div>

						<h3
							class="pl-12 mt-3 text-sm font-medium leading-5 text-gray-800 truncate sm:text-base lg:text-sm 
							"
						>
							Jane Cooper
							<span class="mt-1 text-sm leading-5 text-gray-500 truncate">- CEO SomeCompany</span>
						</h3>
					</div>
					<img
						class="flex-shrink-0 w-20 h-20 bg-gray-300 rounded-full xl:w-24 xl:h-24"
						src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&amp;ixid=eyJhcHBfaWQiOjEyMDd9&amp;auto=format&amp;fit=facearea&amp;facepad=4&amp;w=256&amp;h=256&amp;q=60"
						alt=""
					/>
				</blockquote>
				<blockquote
					class="flex items-center justify-between w-full col-span-1 p-6 mt-4 bg-white rounded-lg shadow"
				>
					<div class="flex flex-col pr-10">
						<div class="relative pl-12">
							<svg
								class="absolute left-0 w-10 h-10 text-indigo-500 fill-current"
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 100 125"
							>
								<path
									d="M30.7 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2C12.7 83.1 5 72.6 5 61.5c0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S30.7 31.6 30.7 42zM82.4 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2-11.8 0-19.5-10.5-19.5-21.6 0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S82.4 31.6 82.4 42z"
								/>
							</svg>
							<p class="mt-2 text-sm text-gray-600 sm:text-base lg:text-sm xl:text-base">
								I can't express enough, how amazing this service has been for my company.
							</p>
						</div>
						<h3
							class="pl-12 mt-3 text-sm font-medium leading-5 text-gray-800 truncate sm:text-base lg:text-sm "
						>
							John Doe
							<span class="mt-1 text-sm leading-5 text-gray-500 truncate">- CEO SomeCompany</span>
						</h3>
						<p class="mt-1 text-sm leading-5 text-gray-500 truncate" />
					</div>
					<img
						class="flex-shrink-0 w-24 h-24 bg-gray-300 rounded-full"
						src="https://images.unsplash.com/photo-1527980965255-d3b416303d12?ixlib=rb-1.2.1&amp;ixid=eyJhcHBfaWQiOjEyMDd9&amp;aauto=format&amp;fit=facearea&amp;facepad=4&amp;w=256&amp;h=256&amp;q=60"
						alt=""
					/>
				</blockquote>
				<blockquote
					class="flex items-center justify-between w-full col-span-1 p-6 mt-4 bg-white rounded-lg shadow"
				>
					<div class="flex flex-col pr-10">
						<div class="relative pl-12">
							<svg
								class="absolute left-0 w-10 h-10 text-indigo-500 fill-current"
								xmlns="http://www.w3.org/2000/svg"
								viewBox="0 0 100 125"
							>
								<path
									d="M30.7 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2C12.7 83.1 5 72.6 5 61.5c0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S30.7 31.6 30.7 42zM82.4 42c0 6.1 12.6 7 12.6 22 0 11-7.9 19.2-18.9 19.2-11.8 0-19.5-10.5-19.5-21.6 0-19.2 18-44.6 29.2-44.6 2.8 0 7.9 2 7.9 5.4S82.4 31.6 82.4 42z"
								/>
							</svg>
							<p class="mt-2 text-sm text-gray-600 sm:text-base lg:text-sm xl:text-base">
								I can't express enough, how amazing this service has been for my company.
							</p>
						</div>

						<h3
							class="pl-12 mt-3 text-sm font-medium leading-5 text-gray-800 truncate sm:text-base lg:text-sm "
						>
							John Smith
							<span class="mt-1 text-sm leading-5 text-gray-500 truncate">- CEO SomeCompany</span>
						</h3>
						<p class="mt-1 text-sm leading-5 text-gray-500 truncate" />
					</div>
					<img
						class="flex-shrink-0 w-24 h-24 bg-gray-300 rounded-full"
						src="https://images.unsplash.com/photo-1545167622-3a6ac756afa4?ixlib=rrb-1.2.1&amp;ixid=eyJhcHBfaWQiOjEyMDd9&amp;aauto=format&amp;fit=facearea&amp;facepad=4&amp;w=256&amp;h=256&amp;q=60"
						alt=""
					/>
				</blockquote>
			</div>
		</div>
	</div>
</section>

<!-- Section 3 -->
<section class="px-2 py-32 bg-white md:px-0">
	<div class="container items-center max-w-6xl px-8 mx-auto xl:px-5">
		<div class="flex flex-wrap items-center sm:-mx-3">
			<div class="w-full md:w-1/2 md:px-3">
				<div
					class="w-full pb-6 space-y-6 sm:max-w-md lg:max-w-lg md:space-y-4 lg:space-y-8 xl:space-y-9 sm:pr-5 lg:pr-0 md:pb-0"
				>
					<h1
						class="text-4xl font-extrabold tracking-tight text-gray-900 sm:text-5xl md:text-4xl lg:text-5xl xl:text-6xl"
					>
						<span class="block xl:inline">Beautiful Pages to</span>
						<span class="block text-indigo-600 xl:inline">Tell Your Story!</span>
					</h1>
					<p class="mx-auto text-base text-gray-500 sm:max-w-md lg:text-xl md:max-w-3xl">
						It's never been easier to build beautiful websites that convey your message and tell
						your story.
					</p>
					<div class="relative flex flex-col sm:flex-row sm:space-x-4">
						<a
							href="#_"
							class="flex items-center w-full px-6 py-3 mb-3 text-lg text-white bg-indigo-600 rounded-md sm:mb-0 hover:bg-indigo-700 sm:w-auto"
						>
							Try It Free
							<svg
								xmlns="http://www.w3.org/2000/svg"
								class="w-5 h-5 ml-1"
								viewBox="0 0 24 24"
								fill="none"
								stroke="currentColor"
								stroke-width="2"
								stroke-linecap="round"
								stroke-linejoin="round"
							>
								<line x1="5" y1="12" x2="19" y2="12" class="" />
								<polyline points="12 5 19 12 12 19" class="" />
							</svg>
						</a>
						<a
							href="#_"
							class="flex items-center px-6 py-3 text-gray-500 bg-gray-100 rounded-md hover:bg-gray-200 hover:text-gray-600"
						>
							Learn More
						</a>
					</div>
				</div>
			</div>
			<div class="w-full md:w-1/2">
				<div class="w-full h-auto overflow-hidden rounded-md shadow-xl sm:rounded-xl">
					<img
						src="https://cdn.devdojo.com/images/november2020/hero-image.jpeg"
						alt="cool heros showing"
					/>
				</div>
			</div>
		</div>
	</div>
</section>

<style>
	div :global(#color-pips) {
		height: 15px;
	}
	div :global(#color-pips .rangeBar) {
		height: 15px;
	}
	div :global(#color-pips .rangeHandle) {
		top: 7px;
		height: 35px;
		width: 35px;
	}
	div :global(#color-pips .rangeHandle .rangeNub) {
		border: 3px solid rgb(246, 252, 255);
	}
	div :global(#color-pips .rangePips) {
		bottom: 0px;
		z-index: 1;
	}
	div :global(#color-pips .rangePips .pip) {
		background: rgb(246, 252, 255);
		border-radius: 30px;
		width: 10px;
		height: 10px;
		transform: translateX(-50%);
	}
	div :global(#color-pips .rangePips .pip.in-range) {
		background: rgb(0, 0, 0);
		opacity: 0.35;
	}
</style>
