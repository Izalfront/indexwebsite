<script lang="ts">
	import { Database, PlayCircle, MoreVertical } from 'lucide-svelte';

	let sqlQuery = `SELECT city, COUNT(*) AS num_orders
  FROM orders
  GROUP BY city
  ORDER BY num_orders DESC
  LIMIT 100;`;
</script>

<div class="bg-white rounded-lg shadow-md overflow-hidden border">
	<div class="flex justify-between items-center px-4 py-2 bg-gray-50 border-b">
		<div class="flex space-x-10">
			<button class="text-gray-600 hover:text-gray-800">
				<Database class="w-5 h-5" />
			</button>
			<span class="font-medium text-gray-700">Preview</span>
			<span class="font-medium text-blue-600 pr-4">&lt;/&gt; SQL</span>
		</div>
		<div class="flex items-center space-x-10">
			<button class="text-gray-600 hover:text-gray-800">Format</button>
			<button
				class="bg-gray-600 text-white px-2 py-1 rounded-md flex font-normal text-xs items-center space-x-1 hover:bg-gray-700"
			>
				<PlayCircle class="w-4 h-4" />
				<span>Run</span>
			</button>
			<button class="text-gray-600 hover:text-gray-800">
				<MoreVertical class="w-5 h-5" />
			</button>
		</div>
	</div>
	<div class="p-4 bg-gray-100 text-left">
		<pre class="font-mono text-sm">
<span class="text-orange-600">1</span> <span class="text-purple-600">SELECT</span> city, <span
				class="text-blue-600">COUNT</span
			>(*) <span class="text-purple-600">AS</span> num_orders
<span class="text-orange-600">2</span> <span class="text-purple-600">FROM</span> orders
<span class="text-orange-600">3</span> <span class="text-purple-600">GROUP BY</span> city
<span class="text-orange-600">4</span> <span class="text-purple-600">ORDER BY</span
			> num_orders <span class="text-purple-600">DESC</span>
<span class="text-orange-600">5</span> <span class="text-purple-600">LIMIT</span> <span
				class="text-green-600">100</span
			>;
    </pre>
	</div>
</div>
