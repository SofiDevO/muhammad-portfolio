<script>
	import '../global.css';
	import Hero from './hero/+page.svelte';
	let { children } = $props();
</script>

<main class="main">
	<Hero />
	<section class="projects">
		<nav class="header__nav">
			<a class="link" href="/">About</a>
			<a class="link" href="/portfolio">Portfolio</a>
			<a class="link" href="/social-links">My Socials</a>
		</nav>
		{@render children()}
	</section>
</main>

<style>
	main {
		display: flex;
		gap: 5rem;
		min-height: 100dvh;
		width: 100%;
		max-width: 1350px;
		margin: 8rem auto;
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
		width: 100%;
	}
	.header__nav {
		display: flex;
		gap: 1.5rem;
		margin-bottom: 2.4rem;
	}
</style>
