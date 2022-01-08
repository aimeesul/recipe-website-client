<script>
	export let recipes;

	// let recipes = [];

	// fetch("http://localhost:3000/recipes")
	// 	.then((response) => response.json())
	// 	.then((data) => {
	// 		for (const item of data) {
	// 			console.log(item.name);
	// 		}

	// 		recipes = data;
	// 	});
</script>

<div class="recipes">
	<div><h1>recipes</h1></div>

	<div>
		{#if recipes == null}
			<div>loading</div>
		{:else}
			{#each recipes as recipe}
				<div>{recipe.name}</div>
			{/each}
		{/if}
	</div>
</div>

<style>
	.recipes {
		text-align: left;
	}
</style>
