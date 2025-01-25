<script>
	import { t } from 'svelte-i18n';

	import Slider from '../Slider/Slider.svelte';

	import './style.scss';
</script>

<div class="how">
	<div class="container">
		<div class="how__slide itemHideLeft animaItemHide" aria-hidden="true">
			<Slider />
		</div>
		<div class="how__list itemHideRight animaItemHide">
			<h2>{$t('how.title')}</h2>
			<ul>
				{#each $t('how.text') as how}
					<li>{how}</li>
				{/each}
			</ul>
		</div>
	</div>
</div>
