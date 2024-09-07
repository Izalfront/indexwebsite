<script lang="ts">
	import UserSign from './child/UserSign.svelte';
</script>

<div class="bg-white p-4 card shadow-sm border rounded-lg mt-6 h-full w-full">
	<div class="container mx-auto">
		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
			<UserSign />
			<UserSign />
			<UserSign />

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
