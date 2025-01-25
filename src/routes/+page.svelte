<script>
	import About from '../lib/organism/About/About.svelte';
	import Hero from '../lib/organism/Hero/Hero.svelte';
	import Works from '../lib/organismComplex/Works/Works.svelte';
	import Servicos from '../lib/organismComplex/Servicos/Servicos.svelte';
	import How from '../lib/organism/How/How.svelte';
	import Cta from '../lib/organism/Cta/Cta.svelte';

	import { t } from 'svelte-i18n';
</script>

<svelte:head>
	<title>BG SoftHouse | Desenvolvimento de sites e software</title>
	<meta name="guifarias" content="guifarias.com.br" />
	<link rel="canonical" href="/" />
	<meta
		name="description"
		content="Potencialize sua presença online com a BG Softhouse. Especialistas em desenvolvimento de sites, lojas virtuais, vídeos impactantes, SEO e identidade visual. Destaque-se na web com nossa abordagem personalizada. Entre em contato hoje mesmo"
	/>
	<meta name="robots" content="index, follow" />
</svelte:head>

<Hero text={$t('hero.description')} />
<About />
<Cta />
<Works />
<Servicos />
<How />
