<script lang="ts">
  import Header from "./components/Header.svelte";
  import Timer from "./components/Timer.svelte";
</script>

<main>
  <Header
    title="Countdown"
    description="This application was made with the sole purpose of trying out Svelte."
  />

  <Timer />
</main>

<style>
  :root {
    --primary: #eb6ed4;
    --secondary: #b543f5;
    --mid: #5f46db;
    --contrast: #4175f2;
    --contrast-secondary: #65c8eb;
    --neutral: #f5f5f5;
    --neutral-black: #222020;

	--font-xxsmall: 0.8rem;
	--font-xsmall: 1rem;
	--font-small: 1.2rem;
	--font-medium: 1.4rem;
	--font-large: 1.6rem;
	--font-xlarge: 2rem;
	--font-xxlarge: 2.4rem;
	--font-xxxlarge: 3rem;
	--font-xxxxlarge: 4rem;
  }

  :global(body) {
    background-color: var(--neutral-black);
    color: var(--neutral);
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
