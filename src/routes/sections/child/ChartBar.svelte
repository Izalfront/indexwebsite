<script lang="ts">
	import { onMount } from 'svelte';
	import {
		Chart,
		LineController,
		LineElement,
		PointElement,
		LinearScale,
		Title,
		CategoryScale,
		BarController,
		BarElement
	} from 'chart.js';

	Chart.register(
		LineController,
		LineElement,
		PointElement,
		LinearScale,
		Title,
		CategoryScale,
		BarController,
		BarElement
	);

	let lineChart: Chart | null = null;
	let barChart: Chart | null = null;

	onMount(() => {
		const canvasLine = document.getElementById('lineChart') as HTMLCanvasElement;
		const ctxLine = canvasLine.getContext('2d');

		if (ctxLine) {
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

		const canvasBar = document.getElementById('barChart') as HTMLCanvasElement;
		const ctxBar = canvasBar.getContext('2d');
		if (ctxBar) {
			barChart = new Chart(ctxBar, {
				type: 'bar',
				data: {
					labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
					datasets: [
						{
							label: 'My First Bar Dataset',
							backgroundColor: 'rgba(54, 162, 235, 0.2)',
							borderColor: 'rgb(54, 162, 235)',
							data: [5, 15, 10, 20, 25, 30, 35]
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
	});
</script>

<div class="bg-white p-6 rounded-md border w-auto max-w-full overflow-hidden">
	<div class="flex flex-col md:flex-row flex-wrap justify-between items-center">
		<div class="w-auto h-auto">
			<canvas id="barChart" class="max-w-full"></canvas>
		</div>
	</div>
	<h2 class="text-md mb-4 font-semibold text-gray-700 pt-4 text-center md:text-left">Chart Bar</h2>
</div>
