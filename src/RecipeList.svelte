<script>
	import Recipe from "./Recipe.svelte";
	import Button from "./Button.svelte";
	export let getRecipesFunc;
	let recipePage = undefined;
	const limit = 20;
	let offset = 0;
	let loading = true;

	getRecipesFunc(offset, limit).then((data) => {
		if (data) {
			recipePage = data.items;
		}
		loading = false;
	});

	function getMore() {
		offset += limit;
		loading = true;
		getRecipesFunc(offset, limit).then((data) => {
			recipePage = [...recipePage, ...data.items];
			loading = false;
		});
	}
</script>

<div class="recipes">
	{#if recipePage == null}
		<div>loading</div>
	{:else}
		<div class="recipelist">
			{#each recipePage as recipe}
				<Recipe {recipe} />
			{/each}
		</div>

		{#if loading}
			loading...
		{:else}
			<Button secondary type="button" on:click={() => getMore()}
				>Load more</Button
			>
		{/if}

		<!-- <div>
			Total recipes : {recipePage.totalCount}, offset : {recipePage.offset},
			limit : {recipePage.limit}
		</div> -->
	{/if}
</div>

<style>
	.recipes {
		text-align: left;
	}
	.recipelist {
		display: grid;
		gap: 1.5em;
		grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
	}
</style>
