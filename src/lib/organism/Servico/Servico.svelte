<script>
	export let title = 'Projetos';
	export let text =
		'Hello World Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam laudantium architecto numquam? Voluptatem fuga maxime quos enim, vitae voluptas soluta ipsum labore perferendis odit velit amet hic modi magnam. Veritatis.';

	export let image = '';
</script>

<div class="service">
	<h2>{title}</h2>
	<img src={image} alt="" aria-hidden="true" />
	<p>{text}</p>
</div>

<style>
	.service {
		display: flex;
		flex-direction: column;
		justify-content: end;
		align-items: center;
		text-align: center;
		gap: 32px;
		max-width: 400px;
		width: 70%;
	}
	.service h2 {
		writing-mode: vertical-lr;
	}
	.service img {
		max-width: 150px;
	}

	.service p {
		font-size: 18px;
	}
</style>
