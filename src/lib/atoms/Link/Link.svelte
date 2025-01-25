<script>
	// import { t } from 'svelte-i18n';

	import './style.scss';

	export let text = 'My text';
	export let url = '';
</script>

<a href={url} class="btn" target="_blank" rel="noopener noreferrer">
	{text}
</a>
