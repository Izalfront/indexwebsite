<script lang="ts">
	import CardChart2 from './child/CardChart2.svelte';
	import ChartBar from './child/ChartBar.svelte';
	import UserSign from './child/UserSign.svelte';
	import ConnectDataSection from './ConnectDataSection.svelte';
	import SponsorSection from './SponsorSection.svelte';
</script>

<div class="bg-white p-4 card shadow-sm border rounded-lg mt-6 h-full max-w-full">
	<div class="container mx-auto">
		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
			<CardChart2 />
			<UserSign />
			<ChartBar />

			<div class=" md:col-span-2">
				<UserSign />
			</div>
			<UserSign />

			<UserSign />
			<UserSign />
			<UserSign />
		</div>
	</div>
</div>
<SponsorSection />
<ConnectDataSection />
