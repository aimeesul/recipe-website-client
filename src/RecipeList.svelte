<script>
	import Recipe from "./Recipe.svelte"
	export let recipes;
</script>

<div class="recipes">
	<div><h1>recipes</h1></div>

	<div>
		{#if recipes == null}
			<div>loading</div>
		{:else}
			{#each recipes as recipe}
				<Recipe {recipe}/>
			{/each}
		{/if}
	</div>
</div>

<style>
	.recipes {
		text-align: left;
	}
</style>
