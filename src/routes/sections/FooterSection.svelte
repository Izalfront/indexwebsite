<script lang="ts">
	import { Twitter, Linkedin, Slack, Database, SignalHighIcon, ChartAreaIcon } from 'lucide-svelte';
</script>

<div class="bg-gray-900 text-gray-300 py-12 px-4 sm:px-6 lg:px-8 w-full mx-12 rounded-t-3xl">
	<div class="text-center flex flex-col items-center">
		<img src="./favicon.png" alt="" class="m-6 w-12 h-12" />
		<button
			class="font-medium text-xs no-underline border border-black bg-white text-black rounded-full px-2 py-1 flex items-center gap-1 mb-4"
		>
			<ChartAreaIcon class="w-4 h-4" />
			See data differently
		</button>
		<p class="text-3xl font-semibold text-white pb-2">Analyze. Visualize.<br />Collabrote.</p>
		<p class="text-xs pb-4">The collaborative platform for business analytics.</p>
		<button class="bg-white text-gray-800 py-1 px-2 rounded-md text-xs font-semibold"
			>Get started - for free</button
		>
	</div>
</div>
<footer
	class="bg-gray-800 text-gray-300 py-12 px-4 sm:px-6 lg:px-8 w-full mx-12 rounded-b-3xl border border-gray-600"
>
	<div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-4 gap-8">
		<div class="col-span-1 md:col-span-4 lg:col-span-1">
			<div class="flex items-center mb-4">
				<img src="./favicon.png" alt="" class="mr-4 w-8 h-8" />
				<span class="text-white font-semibold text-lg">Index</span>
			</div>
			<p class="text-sm mb-4">Crafted by hand — Powered by data.</p>
			<div class="flex space-x-4">
				<Twitter class="w-5 h-5" />
				<Linkedin class="w-5 h-5" />
				<Slack class="w-5 h-5" />
			</div>
		</div>

		<div>
			<h3 class="text-white font-semibold mb-3">Features</h3>
			<ul class="space-y-2 text-sm">
				<li>Integrations</li>
				<li>Editor</li>
				<li>Visualisation</li>
				<li>Customisation</li>
				<li>Speed</li>
				<li>Collaboration</li>
				<li>Themes</li>
			</ul>
		</div>

		<div>
			<h3 class="text-white font-semibold mb-3">Company</h3>
			<ul class="space-y-2 text-sm">
				<li>Pricing</li>
				<li>Changelog</li>
				<li>Careers</li>
				<li>Support</li>
				<li>Community</li>
				<li>Book demo</li>
			</ul>
		</div>

		<div>
			<h3 class="text-white font-semibold mb-3">Resources</h3>
			<ul class="space-y-2 text-sm">
				<li>Privacy Policy</li>
				<li>Terms of Services</li>
				<li>Security</li>
				<li>Brand</li>
			</ul>
		</div>
	</div>
</footer>
