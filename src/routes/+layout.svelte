<script lang="ts">
	import { onMount } from 'svelte';
	import '../app.css';

	let isMobileMenuOpen = false;

	function toggleMobileMenu() {
		isMobileMenuOpen = !isMobileMenuOpen;
	}

	onMount(() => {
		const handleResize = () => {
			if (window.innerWidth >= 1024) {
				isMobileMenuOpen = false;
			}
		};

		window.addEventListener('resize', handleResize);

		return () => {
			window.removeEventListener('resize', handleResize);
		};
	});
</script>

<div class="bg-white">
	<header class="bg-white p-4">
		<nav class="mt-2 flex justify-between items-center p-4 text-black mx-4 font-medium">
			<img src="/favicon.png" alt="" class="w-6 h-6" />

			<div class="lg:hidden">
				<button on:click={toggleMobileMenu} class="focus:outline-none">
					<svg
						class="w-6 h-6"
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M4 6h16M4 12h16m-7 6h7"
						/>
					</svg>
				</button>
			</div>

			<ul class="hidden lg:flex space-x-10">
				<li><a href="#" class="hover:underline">Features</a></li>
				<li><a href="#" class="hover:underline">Pricing</a></li>
				<li><a href="#" class="hover:underline">Blog</a></li>
				<li><a href="#" class="hover:underline">Changelog</a></li>
				<li><a href="#" class="hover:underline">Careers</a></li>
				<li><a href="#" class="hover:underline">Support</a></li>
			</ul>

			<a href="#" class="hidden lg:block hover:underline">Log In</a>
		</nav>

		{#if isMobileMenuOpen}
			<ul class="flex flex-col space-y-2 mt-2 mx-4 lg:hidden">
				<li><a href="#" class="hover:underline">Features</a></li>
				<li><a href="#" class="hover:underline">Pricing</a></li>
				<li><a href="#" class="hover:underline">Blog</a></li>
				<li><a href="#" class="hover:underline">Changelog</a></li>
				<li><a href="#" class="hover:underline">Careers</a></li>
				<li><a href="#" class="hover:underline">Support</a></li>
				<li><a href="#" class="hover:underline">Log In</a></li>
			</ul>
		{/if}
	</header>

	<main class="flex flex-col items-center justify-center flex-grow p-4">
		<slot></slot>
	</main>
</div>
