<script>
	import { t } from 'svelte-i18n';
	import DialogContact from '../DialogContact/DialogContact.svelte';
	import './style.scss';
</script>

<section class="cta">
	<div class="container">
		<div class="cta__contact itemHideLeft animaItemHide">
			<h2>{$t('cta.cta_papel')}</h2>
			<div class="cta__btn">
				<DialogContact />
			</div>
		</div>
	</div>
</section>
