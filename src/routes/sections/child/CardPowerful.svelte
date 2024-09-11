<script lang="ts">
	export let cards: { title: string; description: string }[] = [
		{
			title: 'PostgreSQL',
			description:
				'An advanced, open-source relational database known for its high performance and extensibility, ideal for complex queries and large datasets.'
		},
		{
			title: 'MongoDB',
			description:
				'A popular NoSQL database that uses a flexible, document-oriented data model, perfect for handling unstructured data and rapid prototyping.'
		},
		{
			title: 'MySQL',
			description:
				'A widely-used relational database management system known for its reliability, flexibility, and support for SQL, making it a staple in web applications.'
		},
		{
			title: 'Oracle Database',
			description:
				'A powerful, enterprise-grade relational database with strong data security features and high performance for mission-critical applications.'
		},
		{
			title: 'Redis',
			description:
				'An in-memory key-value store renowned for its speed and efficiency, used primarily for caching, real-time analytics, and message brokering.'
		}
	];
</script>

<div class="bg-white p-6 rounded-md border w-auto mx-2">
	<h2 class="text-md font-normal mb-4">Powerful Databases</h2>
	{#each cards as card}
		<div class="mb-4">
			<h3 class="text-lg font-semibold">{card.title}</h3>
			<p class="text-xs leading-normal text-gray-600 mr-12">{card.description}</p>
		</div>
	{/each}
</div>
