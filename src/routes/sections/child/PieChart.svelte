<script lang="ts">
	import { onMount } from 'svelte';
	import { Chart, PieController, ArcElement, CategoryScale, Tooltip, Legend } from 'chart.js';

	Chart.register(PieController, ArcElement, CategoryScale, Tooltip, Legend);

	let pieChart: Chart<'pie', number[], string> | null = null;

	onMount(() => {
		const canvasPie = document.getElementById('pieChart') as HTMLCanvasElement;
		const ctxPie = canvasPie.getContext('2d');

		if (ctxPie) {
			const labels = ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'];
			const numbers = [12, 19, 3, 5, 2, 3];
			pieChart = new Chart(ctxPie, {
				type: 'pie',
				data: {
					labels: labels.map((label, index) => `${label} (${numbers[index]})`),
					datasets: [
						{
							label: 'My First Pie Chart',
							data: [12, 19, 3, 5, 2, 3],
							backgroundColor: [
								'rgba(255, 99, 132, 0.2)',
								'rgba(54, 162, 235, 0.2)',
								'rgba(255, 206, 86, 0.2)',
								'rgba(75, 192, 192, 0.2)',
								'rgba(153, 102, 255, 0.2)',
								'rgba(255, 159, 64, 0.2)'
							],
							borderColor: [
								'rgba(255, 99, 132, 1)',
								'rgba(54, 162, 235, 1)',
								'rgba(255, 206, 86, 1)',
								'rgba(75, 192, 192, 1)',
								'rgba(153, 102, 255, 1)',
								'rgba(255, 159, 64, 1)'
							],
							borderWidth: 1
						}
					]
				},
				options: {
					responsive: true,
					plugins: {
						legend: {
							position: 'top'
						},
						tooltip: {
							callbacks: {
								label: (tooltipItem) => {
									const label = tooltipItem.label || '';
									const value = tooltipItem.raw;
									return `${label}: ${value}`;
								}
							}
						}
					}
				}
			});
		}
	});
</script>

<div class="bg-white p-6 rounded-md border w-auto max-w-full overflow-hidden w-full">
	<div class="flex flex-wrap justify-between items-center">
		<div class="w-auto h-auto">
			<canvas id="pieChart" class="max-w-full"></canvas>
		</div>
	</div>
	<h2 class="text-md mb-4 font-semibold text-gray-700 pt-4">Charts Pie Overview</h2>
</div>
