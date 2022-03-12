<script lang="ts">
	
</script>

<main>
	<h1>Countdown</h1>
	<p>This application was made with the sole purpose of trying out Svelte.</p>
</main>

<style>
	:root {
		--primary: #EB6ED4;
		--secondary: #B543F5;
		--mid: #5F46DB;
		--contrast: #4175F2;
		--contrast-secondary: #65C8EB;
		
		--neutral: #F5F5F5;
		--neutral-black: #222020;
	}

	:global(body) {
		background-color: var(--neutral-black);
		color: var(--neutral);
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: var(--primary);
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>