<script>
	import './style.scss';
	import { onMount, afterUpdate } from 'svelte';

	export let title = 'BG Softhouse';

	let titleAnima = '';
	let index = 0;
	let animationStarted = false;

	function animateTitle() {
		if (index < title.length) {
			titleAnima += title.charAt(index);
			index++;
			setTimeout(animateTitle, 80);
		}
	}

	function handleScroll() {
		if (window.scrollY > 350) {
			const header = document.querySelector('.hero-pages__intro');
			header.classList.add('hero-pages__intro-none');
		} else {
			const header = document.querySelector('.hero-pages__intro');
			header.classList.remove('hero-pages__intro-none');
		}
	}

	onMount(() => {
		if (title) {
			animateTitle();
			animationStarted = true;
		}
		handleScroll();
		window.addEventListener('scroll', handleScroll);
		return () => {
			window.removeEventListener('scroll', handleScroll);
		};
	});

	afterUpdate(() => {
		if (title && !animationStarted) {
			animateTitle();
			animationStarted = true;
		}
	});
</script>

<div class="hero-pages">
	<div class="container">
		<div class="hero-pages__intro">
			<h1>{titleAnima}</h1>
		</div>
	</div>
</div>
