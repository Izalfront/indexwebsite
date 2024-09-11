<script lang="ts">
	import { Database, Settings2Icon } from 'lucide-svelte';
	import CardPowerful from './child/CardPowerful.svelte';
</script>

<div class="bg-gray-50 p-4 sm:p-6 rounded-lg mx-auto my-8 sm:my-14 max-w-7xl">
	<div class="flex flex-col items-center mt-8 sm:mt-12">
		<button
			class="font-medium text-xs no-underline border border-black bg-white text-black rounded-full px-2 py-1 flex items-center gap-1 mb-4"
		>
			<Settings2Icon class="w-4 h-4" />
			Flexibility built-in
		</button>

		<h1 class="text-black text-2xl sm:text-3xl md:text-4xl font-semibold pb-3 text-center">
			Powerful out of the box
		</h1>
		<p
			class="text-xs sm:text-sm text-gray-600 pb-6 sm:pb-8 text-center font-normal leading-normal max-w-xl mx-auto"
		>
			Index is built from ground up to be fast, powerful and delightful to use
		</p>
	</div>
	<div class="container mx-auto">
		<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-2 sm:gap-6">
			{#each Array(6) as _}
				<CardPowerful />
			{/each}
		</div>
	</div>
</div>
