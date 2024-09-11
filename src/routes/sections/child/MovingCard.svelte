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

<div class="card-wrapper py-12 my-12">
	<div class="moving-cards">
		{#each [...cards, ...cards] as card, i (i)}
			<div class="card">
				<h2>{card.title}</h2>
				<p>{card.description}</p>
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
			transform: translateX(-100%);
		}
	}

	.card-wrapper {
		overflow: hidden;
		width: 50%;
		margin: auto;
		padding: 0 1rem;
	}

	.moving-cards {
		display: flex;
		animation: moveHorizontal 20s linear infinite;
	}

	/* Pause animation on hover */
	.card-wrapper:hover .moving-cards {
		animation-play-state: paused;
	}

	.card {
		background-color: white;
		padding: 1rem;
		border-radius: 0.5rem;
		border: 1px solid #e0e0e0;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
		flex-shrink: 0;
		width: 200px;
		margin: 0 0.5rem;
		transition: all 0.3s ease;
	}

	.card:hover {
		box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
	}

	.card h2 {
		font-size: 1rem;
		font-weight: 600;
		margin-bottom: 0.5rem;
	}

	.card p {
		font-size: 0.875rem;
		color: #4a4a4a;
	}

	@media (max-width: 640px) {
		.card {
			width: 200px;
		}
		.card-wrapper {
			overflow: hidden;
			width: 100%;
			margin: auto;
			padding: 0 1rem;
		}
	}
</style>
