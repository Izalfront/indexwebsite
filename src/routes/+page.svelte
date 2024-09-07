<script>
	import DotBackground from '$lib/components/DotBackground.svelte';
	import Introduction from './sections/Introduction.svelte';
</script>

<DotBackground>
	<p
		class="relative z-20 bg-gradient-to-b from-neutral-200 to-neutral-500 bg-clip-text py-8 text-4xl font-bold text-transparent sm:text-7xl"
	></p>
	<div class="block text-center">
		<p class="text-center text-5xl text-gray-800 font-semibold">
			Data to <span class="text-orange-500">insights</span><br />
			in minutes
		</p>
		<p class="text-center p-4">
			Explore your data, build your dashboard,<br />
			bring your team together.
		</p>
		<button
			class="bg-gray-900 text-white font-semibold mt-2 py-2 px-4 rounded shadow-lg hover:shadow-xl hover:bg-gray-950 transition"
		>
			Get started
		</button>
	</div>
</DotBackground>
<div class="columns-1">
	<Introduction />
</div>
