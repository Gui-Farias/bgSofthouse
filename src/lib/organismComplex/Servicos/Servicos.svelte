<script>
	import { t } from 'svelte-i18n';

	import Servico from '../../organism/Servico/Servico.svelte';

	import './style.scss';

	//parte pra verificar qual o icone, trazendo direto do json nao faz o preload e nao carrega em producao
	import IconSites from '$lib/assets/iconWeb.png';
	import IconLogo from '$lib/assets/iconLogo.png';
	import IconLojas from '$lib/assets/iconEcomerce.png';
	import IconVideo from '$lib/assets/iconVideo.png';

	const serviceIcon = (service) => {
		switch (service) {
			case 'Sites':
				return IconSites;
			case 'Logo':
				return IconLogo;
			case 'Lojas':
			case 'Stores':
				return IconLojas;
			case 'Video':
			case 'Vídeo':
				return IconVideo;
			default:
				return '/';
		}
	};

	// // Função para obter três itens aleatórios de um array
	function getThreeRandomItems(array) {
		if (!Array.isArray(array)) {
			return [];
		}
		// Embaralhar o array
		const shuffledArray = array.sort(() => Math.random() - 0.5);
		// Selecionar os três primeiros itens
		return shuffledArray.slice(0, 3);
	}

	let servicesList = [];
	$: servicesList = getThreeRandomItems($t('services'));
</script>

<div class="servicos" id="services">
	<div class="container">
		<div class="servicos__container itemHideTop animaItemHide">
			{#each servicesList as services}
				<Servico title={services.name} text={services.text} image={serviceIcon(services.name)} />
			{/each}
		</div>
	</div>
</div>
