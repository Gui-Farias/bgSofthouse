<script>
	import { locale } from 'svelte-i18n';

	import pt from '$lib/translate/icon-pt.png';
</script>

<button on:click={() => ($locale = 'pt')} aria-label="Site em portugues" lang="pt">
	<img src={pt} alt="" title="Site em portugues" />
</button>

<style>
	button:focus-visible {
		outline: 4px solid var(--color-secondary);
	}
</style>
