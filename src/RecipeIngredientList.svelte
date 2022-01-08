<script>
	import RecipeIngredient from "./RecipeIngredient.svelte"
	export let recipeIngredientList;
</script>

<div>
	{#each recipeIngredientList as recipeIngredient}
		<div><RecipeIngredient {recipeIngredient}/></div>	
	{/each}
</div>
