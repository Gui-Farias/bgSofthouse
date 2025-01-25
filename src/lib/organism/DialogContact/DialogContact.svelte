<script>
	import Form from '$lib/moleculs/Form/Form.svelte';
	import './style.scss';

	import { onMount } from 'svelte';
	import { t } from 'svelte-i18n';

	onMount(() => {
		// Obtém referências para os botões, o diálogo e a sobreposição
		const openDialogButtons = document.querySelectorAll('.openDialogButton');
		const dialog = document.querySelector('.dialog');
		const closeDialogButton = document.querySelector('.closeDialogButton');
		const overlay = document.querySelector('.overlay');

		// Função para abrir o diálogo
		const openDialog = () => {
			dialog.showModal(); // Mostra o diálogo
			overlay.classList.add('block'); // Adiciona a classe de fundo no overlay
		};

		// Função para fechar o diálogo
		const closeDialog = () => {
			dialog.close(); // Fecha o diálogo
			overlay.classList.remove('block'); // remove a sobreposição
		};

		// Adiciona um evento de clique a cada botão para abrir o diálogo
		openDialogButtons.forEach((button) => {
			button.addEventListener('click', openDialog);
		});

		// Adiciona um evento de clique ao botão de fechar para fechar o diálogo
		closeDialogButton.addEventListener('click', closeDialog);

		// Adiciona um evento de teclado para fechar o diálogo com a tecla Esc
		dialog.addEventListener('keydown', (event) => {
			if (event.key === 'Escape') {
				closeDialog(); // Chama a função para fechar o diálogo
			}
		});
	});
</script>

<button class="openDialogButton btn">{$t('buttons.contact')}</button>

<div class="">
	<!-- Sobreposição escura -->
	<div class="overlay"></div>

	<!-- Diálogo -->
	<dialog class="dialog">
		<h2>{$t('form.title')}</h2>
		<p>{$t('form.text')}</p>
		<button class="closeDialogButton scaleItemUp">X</button>

		<Form />
	</dialog>
</div>
