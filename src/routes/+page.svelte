<script>
	import '../global.css';
	import Hero from '$lib/components/hero/Hero.svelte';
</script>

<main class="main">
	<Hero />
	<section class="projects">
		<h1>Projects</h1>
		<p>
			Lorem ipsum, dolor sit amet consectetur adipisicing elit. Provident nemo totam est corporis
			tempore culpa voluptates qui fugit, dignissimos aliquid magni at error architecto aliquam
			accusamus quos neque iure eaque.
		</p>
	</section>
</main>

<style>
	main {
		display: flex;
		margin-top:10rem;
		gap: 5rem;
		padding: 8rem 2rem;
		min-height: 100dvh;
		@media (width < 768px) {
			flex-direction: column;
		}
	}
	.projects {
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		gap: 1rem;
		min-height: 100dvh;
	}
</style>
