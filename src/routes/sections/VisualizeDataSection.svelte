<script lang="ts">
	import { Database } from 'lucide-svelte';
	import UserSign from './child/UserSign.svelte';
	import CardChart from './child/CardChart.svelte';
</script>

<div class="flex flex-col items-center p-6 mt-12">
	<button
		class="font-medium text-xs no-underline border border-black bg-white text-black rounded-full px-2 py-1 flex items-center gap-1 mb-4"
	>
		<Database class="w-4 h-4" />
		Data harmony
	</button>

	<p class="text-black text-4xl font-semibold pb-3 text-center">
		Visualize data<br />with powerful charts
	</p>
	<p class="text-xs text-gray-600 pb-8 text-center font-normal leading-normal">
		Visualize your data in a variety of ways thanks to a robust set of visualizations.<br />
		Whether it's as a table, a chart, or a single value -- you're in control.
	</p>
	<div class="bg-white p-4 card shadow-sm border rounded-lg mt-6 h-full w-full">
		<div class="container mx-auto">
			<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
				<CardChart />
				<!-- <CardChart />
				<CardChart />

				<div class=" md:col-span-2">
					<CardChart />
				</div>
				<CardChart />

				<CardChart />
				<CardChart />
				<CardChart /> -->
			</div>
		</div>
	</div>
</div>
