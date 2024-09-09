<script lang="ts">
	import { onMount } from 'svelte';
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

	let chart: Chart | null = null;

	onMount(() => {
		const canvas = document.getElementById('myChart') as HTMLCanvasElement;
		const ctx = canvas.getContext('2d');

		if (ctx) {
			chart = new Chart(ctx, {
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
	});
</script>

<div class="bg-white p-6 rounded-md border w-auto">
	<div style="width: 100%; height: 400px;">
		<canvas id="myChart"></canvas>
	</div>
	<h2 class="text-md font-normal mb-4">Card Chart</h2>
</div>
