<script>
	import { t } from 'svelte-i18n';

	import SectionIntro from '../../moleculs/SectionIntro/SectionIntro.svelte';
	import Logo from '$lib/assets/logoBlack.webp';

	import './style.scss';
</script>

<section class="about" id="about">
	<div class="container">
		<div class="about__contText itemHideLeft animaItemHide">
			<SectionIntro title={$t('about.title')} text={$t('about.description')} />
		</div>
		<div class="about__logo itemHideRight animaItemHide">
			<img src={Logo} alt="" />
		</div>
	</div>
</section>
