<hero class="hero">
	<div class="hero__wrapper">
		<img
			src="/images/avatar.png"
			alt="profiler avatar of Angela Sofía Osorio"
			class="hero__image"
			width="240"
			height="240"
		/>
		<div class="hero__container">
			<h2 class="hero__name">Angela Sofía Osorio</h2>
			<p class="hero__description">Javascript developer</p>
		</div>
	</div>
</hero>

<style>
	.hero {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 1rem;
	}
	.hero__wrapper {
		position: relative;

	}
	.hero__container {
		height: 311px;
		width:35.2rem;
		background: linear-gradient(180deg, #2f3d59 0%, #0b1326 100%);
		border: 1px solid #6f7a8fb3;
		background-size: contain;
		background-position: center;
		background-repeat: no-repeat;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		border-radius: 39px;
		position: relative;
		clip-path: path(
			'M69 0H32C14.33 0 0 14.33 0 32V336C0 353.67 14.33 368 32 368H321C338.67 368 353 353.67 353 336V32C353 14.33 338.67 0 321 0H285C278 0 272 5 272 10V44C272 72 272 88 264 96C256 104 240 108 221 108H133C114 108 98 104 90 96C82 88 82 72 82 44V10C82 5 76 0 69 0Z'
		);
	}
	.hero__image {
		width: 100%;
		height: auto;
		max-width: 251px;
		position: absolute;
		z-index: 10;
		left: 8.8rem;
		top: -12.4rem;
		width: 100%;
		height: auto;
		max-width: 180px;
		position: absolute;
		z-index: 10;
		left: 8.7rem;
		top: -6.4rem;
	}
</style>
