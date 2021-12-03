<script>
	import RangeSlider from 'svelte-range-slider-pips';

	let values = [10, 40];

	let hue = [360];
	$: lightColor = `hsl(${Math.round(hue[0] - 10)}, 66%, 51%)`;
	$: color = `hsl(${Math.round(hue[0])}, 66%, 54%)`;
	$: formatedHue = Math.round(hue / 10);

	let styles = {
		'note-bg-color': '#f4ed2a',
		'note-color': '#FF5555',
		bg: '#AAAAAA'
	};

	$: cssVarStyles = Object.entries(styles)
		.map(([key, value]) => `--${key}:${value}`)
		.join(';');
</script>

<section class="w-full px-3 lg:px-6">
	<div class="mx-auto max-w-7xl">
		<nav class="flex items-center w-full h-24 select-none">
			<div
				class="relative flex flex-wrap items-center justify-between w-full h-24 mx-auto font-medium md:justify-center"
			>
				<a href="#_" class="md:w-1/4 py-4 pl-6 pr-4 md:pl-4 md:py-0">
					<span class="p-1 text-xl font-black leading-none text-white select-none"
						><span class="text-primary md:text-xl text-4xl">AXperimentalists</span><span
							class="text-indigo-300">.</span
						></span
					>
				</a>
				<div
					class="fixed top-0 left-0 z-40 items-center hidden w-full h-full p-3 text-xl bg-gray-900 bg-opacity-50 md:text-sm lg:text-base md:w-3/4 md:bg-transparent md:p-0 md:relative md:flex"
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
								class="inline-block  px-4 py-2 mx-2 font-medium text-left md:px-0 hover:text-indigo-800 md:hover:text-white lg:mx-3 md:text-center"
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
					class="absolute right-0 z-50 flex flex-col items-end w-10 h-10 p-2 mr-4 rounded-full cursor-pointer md:hidden hover:bg-gray-900 hover:bg-opacity-10 text-gray-100"
				>
					<svg
						class="w-6 h-6"
						x-show="!showMenu"
						fill="none"
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path d="M4 6h16M4 12h16M4 18h16" />
					</svg>
					<svg
						class="w-6 h-6"
						x-show="showMenu"
						fill="none"
						stroke="currentColor"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
						style="display: none;"
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
		<div class="container py-12 md:py-32 mx-auto text-center sm:px-4">
			<h1
				class="text-4xl font-extrabold leading-10 tracking-tight text-white sm:text-5xl sm:leading-none md:text-6xl xl:text-7xl"
			>
				<span class="block">How would you rate your service</span>
				<span class="relative inline-block mt-3 text-white">with us?</span>
			</h1>
			<div class="mr-10 mt-20">
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
				<div class="grid h-auto mx-11 md:mx-36 lg:mx-48">
					<div class="card bg-indigo-400 shadow-md">
						<div class="card-title">
							<div class="stat place-items-center place-content-center bg-indigo-400">
								<div class="stat-title text-white text-3xl md:text-4xl">Net Promoterscore</div>
								<div class="stat-value text-indigo-100 text-6xl">{formatedHue}</div>
								<div class="mt-4 stat-desc text-secondary bg-indigo-400">↗︎ 400 (22%)</div>
							</div>
						</div>
					</div>
				</div>

				<div id="top" style={cssVarStyles}>
					<div class="avatar placeholder mt-11">
						<div class="note text-neutral-content rounded-full w-44 h-44">
							<span class="text-indigo-100 text-6xl font-bold">{formatedHue}</span>
						</div>
					</div>
				</div>
				<input style="padding:0" type="color" bind:value={styles['note-bg-color']} />
			</div>

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
						data-form-type="other"
					>
						<svg
							xmlns="http://www.w3.org/2000/svg"
							class="h-6 w-6 rotate-90"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8"
							/>
						</svg>
					</button>
				</span>
			</div>
			<div class="mt-8 text-sm text-indigo-300">
				By sending, you agree to our terms and services.
			</div>
		</div>
	</div>
</section>

<style>
	.note {
		background-color: var(--note-bg-color, lightgray);
	}

	div :global(#color-pips) {
		height: 20px;
	}
	div :global(#color-pips .rangeBar) {
		height: 22px;
	}
	div :global(#color-pips .rangeHandle) {
		top: 7px;
		height: 50px;
		width: 50px;
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
