<script>
	import './style.scss';

	export function AnimaScroll(items) {
		items.forEach((item) => {
			const rect = item.getBoundingClientRect();
			const viewportHeight = window.innerHeight || document.documentElement.clientHeight;

			// Se o item estiver pelo menos 75% visível, adiciona a classe 'visible'
			if (rect.top < viewportHeight * 0.75 && rect.bottom > 0) {
				item.classList.add('visible');
			} else {
				item.classList.remove('visible');
			}
		});
	}
</script>
