<script lang="ts">
	import { onMount } from 'svelte';
	import { Chart, ArcElement, Tooltip, Legend } from 'chart.js';
	import { Pie } from 'svelte-chartjs';

	Chart.register(ArcElement, Tooltip, Legend);

	interface CityRevenue {
		city: string;
		revenue: number;
		color: string;
	}

	const cityData: CityRevenue[] = [
		{ city: 'Toronto', revenue: 36.12, color: '#F87171' },
		{ city: 'Vancouver', revenue: 31.89, color: '#60A5FA' },
		{ city: 'Montreal', revenue: 14.72, color: '#818CF8' },
		{ city: 'Other', revenue: 17.27, color: '#E5E7EB' }
	];

	const data = {
		labels: cityData.map((item) => item.city),
		datasets: [
			{
				data: cityData.map((item) => item.revenue),
				backgroundColor: cityData.map((item) => item.color),
				borderColor: cityData.map((item) => item.color),
				borderWidth: 1
			}
		]
	};

	const options = {
		responsive: true,
		plugins: {
			legend: {
				position: 'top'
			},
			tooltip: {
				callbacks: {
					label: function (context) {
						let label = context.label || '';
						if (label) {
							label += ': ';
						}
						if (context.parsed !== null) {
							label += context.parsed.toFixed(2) + '%';
						}
						return label;
					}
				}
			}
		}
	};

	const totalRevenue = cityData.reduce((sum, item) => sum + item.revenue, 0);

	let chart;

	onMount(() => {
		// Jika diperlukan, Anda bisa melakukan operasi tambahan pada chart di sini
	});
</script>

<div class="bg-white p-6 rounded-lg border w-auto">
	<h2 class="text-lg font-semibold mb-4">Revenue by city</h2>
	<div class="relative">
		<Pie {data} {options} bind:chart />
		<div class="absolute inset-0 flex items-center justify-center flex-col">
			<span class="text-sm text-gray-500">Total</span>
			<span class="text-2xl font-bold">{totalRevenue.toFixed(2)}m</span>
		</div>
	</div>
</div>
