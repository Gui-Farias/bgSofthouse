<script>
	import SectionIntro from '$lib/moleculs/SectionIntro/SectionIntro.svelte';
	import { t } from 'svelte-i18n';

	import './style.scss';

	export let title = 'Projetos';
	export let text =
		'Hello World Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam laudantium architecto numquam? Voluptatem fuga maxime quos enim, vitae voluptas soluta ipsum labore perferendis odit velit amet hic modi magnam. Veritatis.';

	export let url = '#';

	import GuiMac from '$lib/assets/pcGui.webp';
	import GuiLocaMac from '$lib/assets/pcGuiLoca.webp';

	const workMac = (project) => {
		switch (project) {
			case 'Gui Locações':
			case 'Gui rentals':
				return GuiLocaMac;
			case 'Gui Farias':
				return GuiMac;
			default:
				return '/';
		}
	};
</script>

<div class="work">
	<div class="work__sectText">
		<SectionIntro {title} {text} link={$t('buttons.project')} {url} />
	</div>

	<div class="work__video">
		<img
			src={workMac(title)}
			alt="Imagem da home do projeto"
			srcset=""
		/>
	</div>
</div>
