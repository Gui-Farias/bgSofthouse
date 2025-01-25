<script>
	import { t } from 'svelte-i18n';

	import Work from '../../organism/Work/Work.svelte';

	import './style.scss';

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

	let workList = [];
	$: workList = getThreeRandomItems($t('works'));
</script>

<div class="works" id="projects">
	<div class="container itemHideLeft animaItemHide">
		{#each workList as work}
			<Work title={work.name} text={work.text} url={work.link} />
		{/each}
	</div>
</div>
