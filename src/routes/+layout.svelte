<script lang="ts">
	import '../app.css';
</script>

<div class="bg-white">
	<header class="bg-white p-4">
		<nav class="mt-2 flex justify-between p-4 text-black mx-4 font-medium">
			<img src="/favicon.png" alt="" class="w-6 h-6" />
			<ul class="flex space-x-10">
				<li><a href="#" class="hover:underline">Features</a></li>
				<li><a href="#" class="hover:underline">Pricing</a></li>
				<li><a href="#" class="hover:underline">Blog</a></li>
				<li><a href="#" class="hover:underline">Changelog</a></li>
				<li><a href="#" class="hover:underline">Careers</a></li>
				<li><a href="#" class="hover:underline">Support</a></li>
			</ul>
			<a href="#" class="hover:underline">Log In</a>
		</nav>
	</header>

	<main class="flex flex-col items-center justify-center flex-grow p-4">
		<slot></slot>
	</main>
</div>
