<script>
	let recipes = [];

	fetch("http://localhost:3000/recipes")
		.then((response) => response.json())
		.then((data) => {
			for (const item of data) {
				console.log(item.name);
			}

			recipes=data;
		});
</script>

<div><h1>recipes</h1></div>

<div>
	{#each recipes as recipe}
		<div>{recipe.name}</div>
	{/each}
</div>

<style>
</style>
