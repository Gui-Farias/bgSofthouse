<script>
	import './style.scss';

	import ButtonPT from '../../atoms/ButtonPT/ButtonPT.svelte';
	import ButtonEN from '../../atoms/ButtonEN/ButtonEN.svelte';
	import DialogContact from '../DialogContact/DialogContact.svelte';
	import IconInsta from '../../atoms/IconInsta/IconInsta.svelte';
</script>

<div class="pre-header">
	<div class="hide">
		<DialogContact />
	</div>
	<div class="container">
		<div class="pre-header__iconInsta">
			<IconInsta />
		</div>
		<ul class="pre-header__main-lang" aria-label="Website languages">
			<li>
				<ButtonPT />
			</li>
			<li>
				<ButtonEN />
			</li>
		</ul>
	</div>
</div>
