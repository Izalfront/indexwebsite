<script lang="ts">
	import { Database, GemIcon, Sun } from 'lucide-svelte';
	import SqlEditor from './child/SqlEditor.svelte';
</script>

<div class="bg-gray-50 p-4 sm:p-6 rounded-lg">
	<div class="flex flex-col items-center">
		<button
			class="font-medium text-xs no-underline border border-black bg-white text-black rounded-full px-2 py-1 flex items-center gap-1 mb-4"
		>
			<GemIcon class="w-4 h-4" />
			Accessible for all
		</button>

		<h1 class="text-black text-2xl sm:text-3xl md:text-4xl font-semibold pb-3 pt-3 text-center">
			Query your data - your way
		</h1>
		<p class="text-xs text-gray-600 pb-8 text-center font-normal leading-normal">
			Streamline your data analysis with our seamless SQL and visual editor.<br /> Give everyone in your
			team the superpowers they need.
		</p>

		<button
			class="bg-white text-black font-normal text-xs mt-2 py-2 px-4 rounded-full border shadow hover:bg-gray-100 transition"
		>
			Query
		</button>

		<div class="w-full mt-8">
			<!-- Mobile view: Card-based layout -->
			<div class="sm:hidden space-y-4">
				{#each Array(4) as _, i}
					<div class="bg-white p-4 rounded-lg shadow border mx-6">
						<div class="grid grid-cols-2 gap-2 text-xs">
							<div><span class="font-medium text-sm">ID:</span> 186352</div>
							<div><span class="font-medium text-sm">Date Joined:</span> 01/31/2022</div>
							<div><span class="font-medium text-sm">City:</span> Vancouver</div>
							<div><span class="font-medium text-sm">Total Spending:</span> $1521.20</div>
							<div><span class="font-medium text-sm">Total Orders:</span> 102</div>
							<div><span class="font-medium text-sm">Last Order:</span> 09/31/2023</div>
							<div>
								<span class="font-medium text-sm">Membership:</span>
								<span class="text-blue-600">Plus</span>
							</div>
						</div>
					</div>
				{/each}
			</div>

			<!-- Desktop view: Table layout -->
			<div class="hidden sm:block overflow-x-auto bg-white rounded-lg shadow border">
				<table class="w-full text-sm text-left">
					<thead class="text-xs uppercase bg-gray-50">
						<tr>
							<th class="px-4 py-3 font-medium text-gray-500">id</th>
							<th class="px-4 py-3 font-medium text-gray-500">date joined</th>
							<th class="px-4 py-3 font-medium text-gray-500">city</th>
							<th class="px-4 py-3 font-medium text-gray-500">total spending</th>
							<th class="px-4 py-3 font-medium text-gray-500">total orders</th>
							<th class="px-4 py-3 font-medium text-gray-500">last order</th>
							<th class="px-4 py-3 font-medium text-gray-500">membership</th>
						</tr>
					</thead>
					<tbody>
						{#each Array(4) as _, i}
							<tr class="border-b">
								<td class="px-4 py-3 font-medium">186352</td>
								<td class="px-4 py-3">01/31/2022</td>
								<td class="px-4 py-3">Vancouver</td>
								<td class="px-4 py-3">$1521.20</td>
								<td class="px-4 py-3">102</td>
								<td class="px-4 py-3">09/31/2023</td>
								<td class="px-4 py-3 text-blue-600">Plus</td>
							</tr>
						{/each}
					</tbody>
					<tfoot>
						<tr class="bg-gray-50">
							<td colspan="3" class="px-4 py-3 font-medium text-gray-500">AVERAGE</td>
							<td class="px-4 py-3 font-medium">$201.53</td>
							<td class="px-4 py-3 font-medium">9</td>
							<td colspan="2"></td>
						</tr>
					</tfoot>
				</table>
			</div>
		</div>

		<div class="py-8 w-full">
			<SqlEditor />
		</div>
	</div>
</div>
