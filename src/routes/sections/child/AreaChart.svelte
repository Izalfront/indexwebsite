<script lang="ts">
	import { onMount } from 'svelte';
	import {
		Chart,
		LineController,
		LineElement,
		PointElement,
		LinearScale,
		Title,
		Tooltip,
		CategoryScale
	} from 'chart.js';

	// Register necessary components for Line (Area) Chart
	Chart.register(
		LineController,
		LineElement,
		PointElement,
		LinearScale,
		Title,
		Tooltip,
		CategoryScale
	);

	let areaChart: Chart<'line', number[], string> | null = null;

	onMount(() => {
		const canvasArea = document.getElementById('areaChart') as HTMLCanvasElement;
		const ctxArea = canvasArea.getContext('2d');

		if (ctxArea) {
			const labels = ['January', 'February', 'March', 'April', 'May', 'June'];
			const numbers = [12, 19, 3, 5, 2, 3];

			areaChart = new Chart(ctxArea, {
				type: 'line',
				data: {
					labels: labels,
					datasets: [
						{
							label: 'Area Chart',
							data: numbers,
							fill: true,
							backgroundColor: 'rgba(75, 192, 192, 0.2)',
							borderColor: 'rgba(75, 192, 192, 1)',
							borderWidth: 1,
							tension: 0.4
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
					},
					scales: {
						x: {
							title: {
								display: true,
								text: 'Month'
							}
						},
						y: {
							title: {
								display: true,
								text: 'Value'
							}
						}
					}
				}
			});
		}
	});
</script>

<div class="bg-white p-6 rounded-md border max-w-full overflow-hidden w-full">
	<div class="flex flex-wrap justify-between items-center">
		<div class="w-full h-auto">
			<canvas id="areaChart" class="max-w-full"></canvas>
		</div>
	</div>
	<h2 class="text-md mb-4 font-semibold text-gray-700 pt-4">Area Chart Overview</h2>
</div>
