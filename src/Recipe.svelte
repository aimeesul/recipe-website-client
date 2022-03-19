<script>
	import RecipeIngredientList from "./RecipeIngredientList.svelte"
	import RecipeStepList from "./RecipeStepList.svelte"
	export let recipe;
</script>

<style>
	div{
		border: 1px solid #aaa;
		box-shadow: 2px 2px 10px #00000080;
		text-indent: 1em;
	}
	
</style>

<div>
	<h2>{recipe.title}</h2>
	<p><b>Ingredients:</b></p>
	<RecipeIngredientList recipeIngredientList={recipe.recipeIngredients}/>
	<p><b>Method:</b></p>
	<RecipeStepList recipeStepList = {recipe.recipeSteps}/>
	<p>Posted by: {recipe.user.userName}</p>
</div>
