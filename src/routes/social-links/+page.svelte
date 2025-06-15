<script>
	import SocialCard from './SocialCard.svelte';
	import data from './socialLinks.json';
	import "./social-links.css";
</script>

<section class="social">

		<ul class="social__grid-container">
			<SocialCard {...data[0]} />
			<SocialCard {...data[1]} />
			<SocialCard {...data[2]} />
			<SocialCard {...data[3]} />
			<SocialCard {...data[4]} />
			<SocialCard {...data[5]} />
			<SocialCard {...data[6]} />
		</ul>
</section>
