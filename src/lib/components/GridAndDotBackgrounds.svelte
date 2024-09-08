<script lang="ts">
	export let showFade: boolean = true;
</script>

<div
	class="relative flex h-96 w-[50vw] items-center justify-center bg-white bg-grid-light-black/[0.1]"
>
	{#if showFade}
		<div
			class="pointer-events-none absolute inset-0 flex items-center justify-center bg-white [mask-image:radial-gradient(ellipse_at_center,transparent_10%,black)]"
		></div>
	{/if}
	<slot />
</div>
