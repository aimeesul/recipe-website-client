<script>
	import RecipeIngredientList from "./RecipeIngredientList.svelte"
	export let recipe;
</script>

<div>
	<h2>{recipe.title}</h2>
	<RecipeIngredientList recipeIngredientList={recipe.recipeIngredients}/>
</div>
