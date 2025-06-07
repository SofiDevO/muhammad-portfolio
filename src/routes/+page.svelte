<script>
	import { Router, Link, Route } from 'svelte-routing';
	import '../global.css';
	import Hero from '$lib/components/hero/Hero.svelte';
	import About from './about/About.svelte';
	import Home from './home/Home.svelte';
	export let url = '';
</script>

<main class="main">
	<Hero />
	<section class="projects">
		<Router {url}>
			<nav class="header__nav">
				<Link class="link" to="/">Home</Link>
				<Link class="link" to="/about">About</Link>
			</nav>
			<div>
				<Route path="/">
					<Home />
				</Route>
				<Route path="/about">
					<About />
				</Route>
			</div>
		</Router>
	</section>
</main>

<style>
	main {
		display: flex;
		gap: 5rem;
		padding: 8rem 2rem;
		min-height: 100dvh;
		width: 100%;
		max-width: 1100px;
		margin: 10rem auto;
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
	.header__nav{
		display: flex;
		gap: 1.5rem;
		margin-bottom: 2.4rem;

	}


</style>
