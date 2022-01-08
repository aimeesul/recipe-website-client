<script>
	import RecipeStep from "./RecipeStep.svelte"
	export let recipeStepList;
</script>

<ol>
	{#each recipeStepList as recipeStep}
		<li><RecipeStep {recipeStep}/></li>	
	{/each}
</ol>
