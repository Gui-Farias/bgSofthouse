<script>
	import { t } from 'svelte-i18n';
	import DialogContact from '../../organism/DialogContact/DialogContact.svelte';

	import './style.scss';

	//check the state of menu
	let isMenuOpen = false;
	function toggleMenu() {
		isMenuOpen = !isMenuOpen;
	}
	function closeMenu() {
		isMenuOpen = false;
	}

	import * as menu from '$lib/translate/pt.json';
	const menuList = menu.menu;

	const linkMenu = (itemKey) => {
		switch (itemKey) {
			case 'home':
				return '/';
			case 'about':
				return '#about';
			case 'work':
				return '#projects';
			case 'service':
				return '#services';
			default:
				return '/';
		}
	};
</script>

<nav class:open={isMenuOpen} class="mainMenu">
	<button on:click={toggleMenu} class="mainMenu__btn-mobile" aria-label="Toggle Menu"></button>
	<ul class="mainMenu__list">
		{#each Object.keys(menuList) as itemKey}
			<li><a href={linkMenu(itemKey)} on:click={closeMenu}>{$t(`menu.${itemKey}`)}</a></li>
		{/each}
		<li>
			<DialogContact />
		</li>
	</ul>
</nav>
