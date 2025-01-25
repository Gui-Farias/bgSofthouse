<script>
	import { t } from 'svelte-i18n';
</script>

<a href="#mainContent">{$t('skip')}</a>

<style>
	a {
		background-color: var(--color-primary);
		box-shadow: 0 0 6px 3px var(--color-neutro-light);
		color: var(--color-secondary);
		font-weight: 700;
		padding: 8px 16px;
		position: absolute;
		top: -50px;
	}

	a:focus {
		top: 0;
		z-index: 100;
	}
</style>
