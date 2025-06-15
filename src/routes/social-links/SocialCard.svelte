<script>
    let { url,icon,title, tag } = $props();
	import "./social-links.css"
</script>


<li class="social__item ">
	<a href={url} class="social__link">
		<div class="content">
			<img src={icon} alt={title} class="social__image" />
			<p>{title}</p>
			<p>{tag}</p>
			<iconify-icon icon="iconamoon:link-external-bold" width="24" height="24"></iconify-icon>
		</div>
	</a>
</li>
