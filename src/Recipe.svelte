<script>
	import RecipeIngredientList from "./RecipeIngredientList.svelte"
	import RecipeStepList from "./RecipeStepList.svelte"
	export let recipe;
</script>

<div>
	<h2>{recipe.title}</h2>
	<RecipeIngredientList recipeIngredientList={recipe.recipeIngredients}/>
	<RecipeStepList recipeStepList = {recipe.recipeSteps}/>

</div>
