<script lang="ts">
	import GridAndDotBackgrounds from '$lib/components/GridAndDotBackgrounds.svelte';
	import { Database } from 'lucide-svelte';
</script>

<div class="bg-white p-6 text-center flex items-center justify-center">
	<GridAndDotBackgrounds>
		<div class="flex flex-col items-center z-10">
			<button
				class="font-medium text-xs no-underline border border-black bg-white text-black rounded-full px-2 py-1 flex items-center gap-1 mb-4"
			>
				<Database class="w-4 h-4" />
				Data harmony
			</button>

			<p class="text-black text-4xl font-semibold pb-3 pt-4 text-center">Connect your data</p>
			<p class="text-sm text-gray-600 pb-8 text-center font-medium">
				Index connects to a growing number of<br />
				databases and data warehouses
			</p>

			<button
				class="bg-gray-900 text-white font-semibold mt-2 py-2 px-4 rounded shadow-lg hover:shadow-xl hover:bg-gray-950 transition"
			>
				Get started today
			</button>
		</div>

		<!-- logo kiri 3 -->
		<div class="bg-transparent z-0 hidden sm:block">
			<div
				class="border absolute top-1/4 w-12 h-12 left-1 bg-white rounded-full shadow-sm flex items-center justify-center"
			>
				<img src="./oracle.png" alt="Oracle Logo" class="w-8 h-8 object-contain" />
			</div>
			<div
				class="border absolute top-10 left-36 w-12 h-12 bg-white rounded-full shadow-sm flex items-center justify-center"
			>
				<img src="./mysql.png" alt="Oracle Logo" class="w-8 h-8 object-contain" />
			</div>
			<div
				class="border absolute bottom-32 left-32 w-12 h-12 bg-white rounded-full shadow-sm flex items-center justify-center"
			>
				<img src="./postgree.png" alt="Oracle Logo" class="w-8 h-8 object-contain" />
			</div>
		</div>
		<!-- logo kanan 3 -->
		<div class="bg-transparent z-0 hidden sm:block">
			<div
				class="border absolute top-1/4 w-12 h-12 right-1 bg-white rounded-full shadow-sm flex items-center justify-center"
			>
				<img src="./docker.png" alt="Oracle Logo" class="w-8 h-8 object-contain" />
			</div>
			<div
				class="border absolute top-10 right-36 w-12 h-12 bg-white rounded-full shadow-sm flex items-center justify-center"
			>
				<img src="./database.png" alt="Oracle Logo" class="w-8 h-8 object-contain" />
			</div>
			<div
				class="border absolute bottom-32 right-32 w-12 h-12 bg-white rounded-full shadow-sm flex items-center justify-center"
			>
				<img src="./aws.png" alt="Oracle Logo" class="w-8 h-8 object-contain" />
			</div>
		</div>
	</GridAndDotBackgrounds>
</div>
