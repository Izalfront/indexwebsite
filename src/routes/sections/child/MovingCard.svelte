<script lang="ts">
	export let cards: { title: string; description: string }[] = [
		{
			title: 'Introduction to Databases',
			description:
				'Learn the basics of databases, including what they are, how they work, and their importance in modern applications.'
		},
		{
			title: 'SQL vs NoSQL Databases',
			description:
				'Understand the differences between SQL and NoSQL databases, including use cases, strengths, and weaknesses of each type.'
		},
		{
			title: 'Database Normalization',
			description:
				'Explore the process of database normalization to eliminate redundancy and ensure data integrity through various normal forms.'
		},
		{
			title: 'Indexing in Databases',
			description:
				'Learn about indexing techniques in databases to optimize query performance and improve data retrieval speed.'
		},
		{
			title: 'ACID Properties in Databases',
			description:
				'Discover the importance of ACID properties (Atomicity, Consistency, Isolation, Durability) in maintaining reliable database transactions.'
		}
	];
</script>

<div class="card-wrapper overflow-hidden relative w-[50%] ml-52 py-12 my-4">
	<div class="moving-cards flex">
		{#each [...cards, ...cards] as card, i (i)}
			<div
				class="card bg-white p-4 rounded-lg border shadow-lg hover:shadow-xl flex-shrink-0 w-60 mx-6"
			>
				<h2 class="text-lg font-semibold mb-2">{card.title}</h2>
				<p class="text-gray-700">{card.description}</p>
			</div>
		{/each}
	</div>
</div>

<style>
	@keyframes moveHorizontal {
		0% {
			transform: translateX(0);
		}
		100% {
			transform: translateX(-70%);
		}
	}

	.card-wrapper {
		overflow: hidden;
		width: 62%; /* Mengatur lebar card-wrapper menjadi 70% */
		margin: auto; /* Mengatur margin untuk sentralisasi */
	}

	.moving-cards {
		display: flex;
		animation: moveHorizontal 20s linear infinite;
	}

	/* Pause animation on hover */
	.card-wrapper:hover .moving-cards {
		animation-play-state: paused;
	}

	/* Smooth transition for hover effect */
	.card {
		transition: all 0.3s ease;
	}
</style>
