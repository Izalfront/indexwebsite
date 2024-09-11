<script lang="ts">
	import { onDestroy, onMount } from 'svelte';
	import {
		Chart,
		LineController,
		LineElement,
		PointElement,
		LinearScale,
		Title,
		CategoryScale
	} from 'chart.js';

	Chart.register(LineController, LineElement, PointElement, LinearScale, Title, CategoryScale);

	let lineChart: Chart | null = null;

	const createChart = () => {
		const canvasLine = document.getElementById('lineChart') as HTMLCanvasElement;
		const ctxLine = canvasLine.getContext('2d');

		if (ctxLine) {
			// Destroy the existing chart if it exists
			if (lineChart) {
				lineChart.destroy();
			}

			// Create a new chart instance
			lineChart = new Chart(ctxLine, {
				type: 'line',
				data: {
					labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
					datasets: [
						{
							label: 'My First dataset',
							backgroundColor: 'rgba(255, 99, 132, 0.2)',
							borderColor: 'rgb(255, 99, 132)',
							data: [0, 10, 15, 10, 20, 14, 40, 60]
						}
					]
				},
				options: {
					responsive: true,
					maintainAspectRatio: false,
					scales: {
						x: {
							type: 'category',
							ticks: {
								maxTicksLimit: 100
							}
						},
						y: {
							type: 'linear',
							ticks: {
								maxTicksLimit: 100
							}
						}
					}
				}
			});
		}
	};

	onMount(() => {
		createChart();
	});

	onDestroy(() => {
		// Clean up the chart instance when the component is destroyed
		if (lineChart) {
			lineChart.destroy();
		}
	});
</script>

<div class="bg-white p-6 rounded-md border w-auto">
	<div class="flex">
		<div style="width: 100%; height: 400px;">
			<canvas id="lineChart"></canvas>
		</div>
	</div>
	<h2 class="text-md font-normal mb-4">Card Chart</h2>
</div>
