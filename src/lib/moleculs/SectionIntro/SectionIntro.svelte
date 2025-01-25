<script>
	import Link from '$lib/atoms/Link/Link.svelte';

	export let title = 'Hello World';
	export let text =
		'Hello World Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam laudantium architecto numquam? Voluptatem fuga maxime quos enim, vitae voluptas soluta ipsum labore perferendis odit velit amet hic modi magnam. Veritatis.';

	export let link = 'false';
	export let url = '#';
</script>

<div class="section-intro">
	<h2>{title}</h2>
	<p>{text}</p>
	<p>
		{#if link != 'false'}
			<Link text={link} {url} />
		{/if}
	</p>
</div>

<style>
	p {
		margin-left: 10%;
		font-size: 24px;
		line-height: 32px;
	}
	p:first-of-type {
		margin-block: 18px 32px;
	}
</style>
