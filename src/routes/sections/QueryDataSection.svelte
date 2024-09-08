<script lang="ts">
	import { Database, GemIcon, Sun } from 'lucide-svelte';
	import SqlEditor from './child/SqlEditor.svelte';
</script>

<div class="bg-gray-50 p-6 rounded-lg">
	<div class="flex flex-col items-center">
		<button
			class="font-medium text-xs no-underline border border-black bg-white text-black rounded-full px-2 py-1 flex items-center gap-1 mb-4"
		>
			<GemIcon class="w-4 h-4" />
			Accessible for all
		</button>

		<p class="text-black text-4xl font-semibold pb-3 pt-3 text-center">
			Query your data - your way
		</p>
		<p class="text-xs text-gray-600 pb-8 text-center font-normal leading-normal">
			Streamline your data analysis with our seamless SQL and visual editor.<br />
			Give everyone in your team the superpowers they need.
		</p>

		<button
			class="bg-white text-black font-normal text-xs mt-2 py-2 px-4 rounded-full border shadow hover:bg-gray-100 transition"
		>
			Query
		</button>
		<br />
		<div class="overflow-x-auto bg-white rounded-lg shadow border">
			<table class="w-full text-sm text-left">
				<thead class="text-xs uppercase bg-gray-50">
					<tr>
						<th class="px-6 py-3 font-medium text-gray-500">id</th>
						<th class="px-6 py-3 font-medium text-gray-500">date joined</th>
						<th class="px-6 py-3 font-medium text-gray-500">city</th>
						<th class="px-6 py-3 font-medium text-gray-500">total spending</th>
						<th class="px-6 py-3 font-medium text-gray-500">total orders</th>
						<th class="px-6 py-3 font-medium text-gray-500">last order</th>
						<th class="px-6 py-3 font-medium text-gray-500">membership</th>
					</tr>
				</thead>
				<tbody>
					<tr class="border-b">
						<td class="px-6 py-4 font-medium">186352</td>
						<td class="px-6 py-4">01/31/2022</td>
						<td class="px-6 py-4">Vancouver</td>
						<td class="px-6 py-4">$1521.20</td>
						<td class="px-6 py-4">102</td>
						<td class="px-6 py-4">09/31/2023</td>
						<td class="px-6 py-4 text-blue-600">Plus</td>
					</tr>
					<tr class="border-b">
						<td class="px-6 py-4 font-medium">186352</td>
						<td class="px-6 py-4">01/31/2022</td>
						<td class="px-6 py-4">Vancouver</td>
						<td class="px-6 py-4">$1521.20</td>
						<td class="px-6 py-4">102</td>
						<td class="px-6 py-4">09/31/2023</td>
						<td class="px-6 py-4 text-blue-600">Plus</td>
					</tr>
					<tr class="border-b">
						<td class="px-6 py-4 font-medium">186352</td>
						<td class="px-6 py-4">01/31/2022</td>
						<td class="px-6 py-4">Vancouver</td>
						<td class="px-6 py-4">$1521.20</td>
						<td class="px-6 py-4">102</td>
						<td class="px-6 py-4">09/31/2023</td>
						<td class="px-6 py-4 text-blue-600">Plus</td>
					</tr>
					<tr class="border-b">
						<td class="px-6 py-4 font-medium">186352</td>
						<td class="px-6 py-4">01/31/2022</td>
						<td class="px-6 py-4">Vancouver</td>
						<td class="px-6 py-4">$1521.20</td>
						<td class="px-6 py-4">102</td>
						<td class="px-6 py-4">09/31/2023</td>
						<td class="px-6 py-4 text-blue-600">Plus</td>
					</tr>
				</tbody>
				<tfoot>
					<tr class="bg-gray-50">
						<td colspan="3" class="px-6 py-3 font-medium text-gray-500">AVERAGE</td>
						<td class="px-6 py-3 font-medium">$201.53</td>
						<td class="px-6 py-3 font-medium">9</td>
						<td colspan="2"></td>
					</tr>
				</tfoot>
			</table>
		</div>
		<div class="flex justify-between items-center mt-4 text-sm">
			<div>
				<button class="px-2 py-1 border rounded-md mr-2">&lt;</button>
				<span class="text-gray-500">1 / 64</span>
				<button class="px-2 py-1 border rounded-md">&gt;</button>
			</div>
		</div>
		<div class="py-8">
			<SqlEditor />
		</div>
	</div>
</div>
