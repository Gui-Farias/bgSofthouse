<script>
	import { t } from 'svelte-i18n';

	import Logo from '$lib/assets/logo.webp';
	import DialogContact from '../DialogContact/DialogContact.svelte';

	import IconInsta from '../../atoms/IconInsta/IconInsta.svelte';

	import './style.scss';

	const dataAtual = new Date();
	const anoAtual = dataAtual.getFullYear();
</script>

<footer class="footer">
	<div class="container">
		<div class="footer__intro itemHideTop animaItemHide">
			<h2>
				{$t('cta.cta_footer')}
			</h2>
			<br /><br />
			<DialogContact />
		</div>
	</div>
	<div class="footer__copyright">
		<p>{$t('footer.copy')} {anoAtual}</p>
		<a href="/" class="footer__copyright-logo" aria-label="Home">
			<img src={Logo} aria-hidden="true" alt="" title="BG Softhouse" />
		</a>
		<div class="footer__copyright-insta">
			<IconInsta />
		</div>
	</div>
</footer>
