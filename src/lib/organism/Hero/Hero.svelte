<script>
	import { onMount } from 'svelte';

	import heroBg from '$lib/assets/hero.svg';
	import './style.scss';

	export let titleh1 = 'BG Softhouse';
	export let text = 'BG Softhouse';

	let index = 0;
	let title = '';

	let heroImg;

	function animateTitle() {
		if (index < titleh1.length) {
			title += titleh1.charAt(index);
			index++;
			setTimeout(animateTitle, 80);
		} else {
			document.querySelector('.hero__intro p').classList.add('hero__intro-animaText');
		}
	}

	function handleScroll() {
		if (window.scrollY > 800) {
			const textIntro = document.querySelector('.hero__intro');
			const imgIntro = document.querySelector('.hero__img');
			textIntro.classList.add('hero__intro-none');
			imgIntro.classList.add('hero__img-none');
		} else {
			const textIntro = document.querySelector('.hero__intro');
			const imgIntro = document.querySelector('.hero__img');
			textIntro.classList.remove('hero__intro-none');
			imgIntro.classList.remove('hero__img-none');
		}
	}

	onMount(() => {
		// heroImg = document.querySelector('.hero__img');
		// heroImg.style.backgroundImage = `url('${heroBg}')`
		// heroImg.style.background = `url('${heroBg}')`

		handleScroll();
		animateTitle();
		window.addEventListener('scroll', handleScroll);
		return () => {
			window.removeEventListener('scroll', handleScroll);
		};
	});
</script>

<div class="hero">
	<div class="container">
		<div class="hero__intro">
			<h1>{title}</h1>
			<p>{text}</p>
		</div>
		<div class="hero__img">
			<img
				src={heroBg}
				width="100%"
				alt="Ilustração animada de um desenvolvedor tendo ideias e digitando em seu computador"
				srcset=""
				preload="none"
			/>
		</div>
	</div>
</div>
