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
		justify-content: space-evenly;
		gap: 5rem;
		padding: 8rem 2rem;
		min-height: 100dvh;
	}
</style>
