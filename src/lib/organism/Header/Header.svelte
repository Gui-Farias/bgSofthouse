<script>
	import Logo from '$lib/atoms/Logo/Logo.svelte';
	import MainMenu from '$lib/moleculs/MainMenu/MainMenu.svelte';

	import './style.scss';

	import { onMount } from 'svelte';

	function handleScroll() {
		if (window.scrollY > 80) {
			const header = document.querySelector('.header');
			header.classList.add('header__scrolled');
		} else {
			const header = document.querySelector('.header');
			header.classList.remove('header__scrolled');
		}
	}

	onMount(() => {
		handleScroll();
		window.addEventListener('scroll', handleScroll);
		return () => {
			window.removeEventListener('scroll', handleScroll);
		};
	});
</script>

<header class="header">
	<div class="container">
		<a href="/">
			<Logo />
		</a>
		<MainMenu />
	</div>
</header>
