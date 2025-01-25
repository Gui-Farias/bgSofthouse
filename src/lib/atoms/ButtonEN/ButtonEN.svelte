<script>
	import { locale } from 'svelte-i18n';

	import en from '$lib/translate/icon-en.png';
</script>

<button on:click={() => ($locale = 'en')} aria-label="Site in English" lang="en">
	<img src={en} alt="" title="English Site" />
</button>

<style>
	button:focus-visible {
		outline: 4px solid var(--color-secondary);
	}
</style>
