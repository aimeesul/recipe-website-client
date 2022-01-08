<script>
	import RecipeList from "./RecipeList.svelte";
	export let name;

	let recipePage = undefined;

	fetch("http://localhost:3000/recipes", {
		headers: { Authorization: "aimeeiscool" },
	})
		.then((response) => response.json())
		.then((data) => {
			recipePage = data;
		});
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>
		Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
		how to build Svelte apps.
	</p>
	<RecipeList {recipePage} />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
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
