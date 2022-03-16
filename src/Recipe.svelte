<script>
	import RecipeIngredientList from "./RecipeIngredientList.svelte"
	import RecipeStepList from "./RecipeStepList.svelte"
	export let recipe;
</script>

<style>
	div{
		border-style: solid;
		width:25em;
		margin: auto;
		text-indent: 1em;
		margin-bottom: 2em;
		margin-top: 2em;
	}
	
</style>

<div>
	<h2>{recipe.title}</h2>
	<p><b>Ingredients:</b></p>
	<RecipeIngredientList recipeIngredientList={recipe.recipeIngredients}/>
	<p><b>Method:</b></p>
	<RecipeStepList recipeStepList = {recipe.recipeSteps}/>
	<p>Posted by: {recipe.userId}</p>
</div>
