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

<div class="mt-6 bg-white p-4 sm:p-6 rounded-md border overflow-hidden w-full">
	<div class="flex flex-col items-center">
		<div class="w-full max-w-xs sm:max-w-sm md:max-w-md lg:max-w-lg xl:max-w-xl">
			<canvas id="areaChart" class="w-full h-auto"></canvas>
		</div>
		<h2 class="text-md mt-4 mb-2 font-semibold text-gray-700 text-center">Area Chart Overview</h2>
	</div>
</div>
