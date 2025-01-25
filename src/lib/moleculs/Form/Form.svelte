<script>
	import './style.scss';
	import { t } from 'svelte-i18n';

	let name = '';
	let phone = '';
	let email = '';
	let choice = '';
	let mensage = '';

	import * as formList from '$lib/translate/pt.json';
	const subjectList = formList.form.subject_list;

	const options = subjectList;

	function sendEmail(name, phone, email, choice, mensage) {
		console.log(name,phone,email,choice,mensage);
	}

	function handleSubmit() {
		// Verificar se todos os campos estão preenchidos
		if (!name || !phone || !email || !choice || !mensage) {
			alert('Por favor, preencha todos os campos.');
			return;
		}

		// Validar o formato do email
		const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
		if (!emailRegex.test(email)) {
			alert('Por favor, insira um endereço de e-mail válido.');
			return;
		}

		// Se todas as validações passarem, exibir as informações no console
		console.log('Nome:', name);
		console.log('Telefone:', phone);
		console.log('Email:', email);
		console.log('Escolha:', choice);
		console.log('mensagem:', mensage);

		sendEmail(name, phone, email, choice, mensage);

		// Limpar os campos do formulário após o envio bem-sucedido
		name = '';
		phone = '';
		email = '';
		choice = '';
		mensage = '';
	}

	// Função para selecionar uma opção da lista suspensa
	function selectOption(option) {
		choice = option;
	}

	// Função para formatar o número de telefone
	function formatPhone() {
		// Remover todos os caracteres que não são dígitos
		const phoneNumber = phone.replace(/\D/g, '');
		// Aplicar a máscara (99) 99999-9999
		if (phoneNumber.length <= 2) {
			phone = `(${phoneNumber}`;
		} else if (phoneNumber.length <= 7) {
			phone = `(${phoneNumber.slice(0, 2)}) ${phoneNumber.slice(2)}`;
		} else {
			phone = `(${phoneNumber.slice(0, 2)}) ${phoneNumber.slice(2, 7)}-${phoneNumber.slice(7, 11)}`;
		}
	}
</script>

<form on:submit|preventDefault={handleSubmit}>
	<label>
		<input type="text" bind:value={name} required placeholder="Nome" />
		<span class="form__span">
			{$t('form.name')}
		</span>
	</label>
	<label>
		<input type="tel" bind:value={phone} required on:input={formatPhone} placeholder="Tel" />
		<span class="form__span">
			{$t('form.tel')}
		</span>
	</label>
	<label>
		<input type="email" bind:value={email} required placeholder="Email" />
		<span class="form__span">
			{$t('form.email')}
		</span>
	</label>
	<label>
		<input type="text" bind:value={choice} required list="options" placeholder="Assunto" />
		<span class="form__span">
			{$t('form.subject')}
		</span>
		<datalist id="options">
			{#each options as option}
				<option value={option} on:click={() => selectOption(option)} />
			{/each}
		</datalist>
	</label>
	<label>
		<textarea bind:value={mensage} required placeholder="Mensagem" class="form__mensage" rows="5"
		></textarea>
		<!-- <input type="text" bind:value={mensage} required  placeholder="Mensagem" class="form__mensage"/> -->
		<span class="form__span">
			{$t('form.message')}
		</span>
	</label>
	<button type="submit">{$t('buttons.form')}</button>
</form>
