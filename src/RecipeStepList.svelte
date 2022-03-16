<script>
	import RecipeStep from "./RecipeStep.svelte"
	export let recipeStepList;
</script>

<style>
	ol{
		padding-left: 0px;
		margin-left: 2em;
	}
</style>
<ol>
	{#each recipeStepList as recipeStep}
		<li><RecipeStep {recipeStep}/></li>	
	{/each}
</ol>
