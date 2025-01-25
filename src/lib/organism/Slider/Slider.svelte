<script>
	import './style.scss';

	import Swiper from 'swiper';
	import 'swiper/swiper-bundle.css';
	import { register } from 'swiper/element/bundle';

	register();
	let mySwiper;

	import { onMount, onDestroy } from 'svelte';

	onMount(() => {
		// Configuração do Swiper com autoplay e navegação
		mySwiper = new Swiper('.swiper-container', {
			autoplay: {
				delay: 3000
			},
			navigation: {
				nextEl: '.swiper-button-next',
				prevEl: '.swiper-button-prev'
			}
		});
	});

	onDestroy(() => {
		if (mySwiper) {
			mySwiper.destroy();
		}
	});

	import slide01 from '$lib/assets/slide01.webp';
	import slide02 from '$lib/assets/slide02.webp';
	import slide03 from '$lib/assets/slide03.webp';
	import slide04 from '$lib/assets/slide04.webp';
	import slide05 from '$lib/assets/slide05.webp';
</script>

<div class="swiper-container container">
	<div class="swiper-wrapper">
		<div class="swiper-slide"><img src={slide01} alt="" loading="lazy" /></div>
		<div class="swiper-slide"><img src={slide02} alt="" loading="lazy" /></div>
		<div class="swiper-slide"><img src={slide03} alt="" loading="lazy" /></div>
		<div class="swiper-slide"><img src={slide04} alt="" loading="lazy" /></div>
		<div class="swiper-slide"><img src={slide05} alt="" loading="lazy" /></div>
	</div>
</div>

<style>
	.container {
		overflow: hidden;
	}

	.swiper-slide {
		max-width: 100%;
		max-height: 350px;
		aspect-ratio: 1;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.swiper-slide img {
		width: 100%;
		max-width: 350px;
		height: auto;
	}
</style>
