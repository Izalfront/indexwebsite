<script lang="ts">
	import { Database, Settings2Icon } from 'lucide-svelte';

	import CardPowerful from './child/CardPowerful.svelte';
</script>

<div class="bg-gray-50 p-6 rounded-lg mx-26 my-14">
	<div class="flex flex-col items-center mt-12">
		<button
			class="font-medium text-xs no-underline border border-black bg-white text-black rounded-full px-2 py-1 flex items-center gap-1 mb-4"
		>
			<Settings2Icon class="w-4 h-4" />
			Flexibility built-in
		</button>

		<p class="text-black text-4xl font-semibold pb-3 text-center">Powerful out of the box</p>
		<p class="text-xs text-gray-600 pb-8 text-center font-normal leading-normal">
			Index is build from ground up to be fast, powerful and delightful to use
		</p>
	</div>
	<div class="container mx-auto">
		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-4">
			<CardPowerful />
			<CardPowerful />
			<CardPowerful />
			<CardPowerful />
			<CardPowerful />
			<CardPowerful />
		</div>
	</div>
</div>
