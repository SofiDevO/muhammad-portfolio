<script lang="ts">
	import data from './portfolio.json';
	import { onMount } from 'svelte';
	let tags: string[] = [];
	let cards: any[] = data;
	const result = data.flatMap((itemTag) => itemTag.tags.map((tag) => tag));
	const uniqueTags = [...new Set(result)];

	const filteredCards = (selectedTag: string) => {
		return data.filter((card) => card.tags.includes(selectedTag));
	};
	onMount(() => {
		const tagButtons = document.querySelector('.tag-list') as HTMLElement;
		tagButtons.addEventListener('click', (event) => {
			const target = event.target as HTMLElement;
			if (target.classList.contains('tag-button')) {
				const selectedTag = target.textContent?.trim();
				if (selectedTag) {
					cards = filteredCards(selectedTag);
				}
			}
		});
	});
</script>

<ul class="tag-list">
	{#each uniqueTags as tag}
		<li class="tag-item">
			<button class="tag-button">
				{tag}
			</button>
		</li>
	{/each}
</ul>
<ul class="grid-container">
	{#each cards as card}
		<article class="card">
			<div class="iamge-container">
				<img src={card.image} alt={card.title} class="card__image" width="300" height="200" />
				<ul class="card__tags">
					{#each card.tags as tag}
						<li class="card__tag">{tag}</li>
					{/each}
				</ul>
			</div>
			<div class="card__content">
				<h2 class="card__title">{card.title}</h2>
				<p class="card__desc">{card.description}</p>
				<div class="card__links">
					<a  aria-label="link to github" href={card.repo} class="card__link">
						<iconify-icon icon="simple-icons:github" width="30" height="30" style="color: #fefe3f"
						></iconify-icon>
					</a>
					<a aria-label="link to project"  href={card.project} class="card__link">
						<iconify-icon icon="ri:link" width="30" height="30" style="color: #fefe3f"
						></iconify-icon>
					</a>
				</div>
			</div>
		</article>
	{/each}
</ul>

<style>
	.tag-list {
		display: flex;
		flex-wrap: wrap;
		gap: 0.9rem;
		margin-bottom: 1rem;
		.tag-button {
			padding: 0.8rem 1rem;
			border-radius: 0.5rem;
			cursor: pointer;
			background-color: var(--golden-color);
			font-weight: 600;
			transition:
				transform 0.2s ease-in-out,
				background-color 0.2s ease-in-out,
				color 0.2s ease-in-out;
			&:hover {
				background-color: black;
				color: var(--golden-color);
				transform: scale(0.95);
			}
		}
	}

	.grid-container {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 289px));
		grid-template-rows: minmax(201px, 350px);
		gap: 2rem;
	}

	.card {
		margin-top: 5rem;
		background-color: rgb(1, 35, 57);
		border-radius: 8px;
		width: 100%;
		overflow: hidden;
		height: 100%;
		display: flex;
		flex-direction: column;
		gap: 2rem;
		.iamge-container {
			position: relative;
			width: 100%;
			overflow: hidden;
			max-height: 156px;
			.card__image {
				width: 100%;
				height: auto;
				object-fit: cover;
				transition: transform 0.4s ease-in-out;
			}
			.card__tags {
				position: absolute;
				bottom: 0;
				left: 0;
				display: flex;
				flex-wrap: wrap;
				gap: 0.5rem;
				padding: 0.5rem;
				.card__tag {
					font-size: 1.2rem;
					background: var(--golden-color);
					padding: 0.5rem 1rem;
					border-radius: 0.5rem;
					color: black;
				}
			}
		}
		.card__content {
			display: flex;
			flex-direction: column;
			gap: 1rem;
			padding: 1rem;
			height: 100%;
		}
		.card__title {
			font-size: 1.8rem;
			font-weight: 600;
		}
		.card__desc {
			font-size: 1.6rem;
		}
		.card__links {
			margin-top: auto;
			display: flex;
			align-items: center;
			gap: 1.5rem;
		}
	}
	.card:hover .card__image {
		transform: scale(1.1);
	}
</style>
