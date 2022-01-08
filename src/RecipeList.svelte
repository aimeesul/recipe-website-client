<script>
	import Recipe from "./Recipe.svelte";
	export let recipePage;
</script>

<div class="recipes">
	<div><h1>recipes</h1></div>

	{#if recipePage == null}
		<div>loading</div>
	{:else}
		{#each recipePage.items as recipe}
			<div>
				<Recipe {recipe} />
			</div>
		{/each}
		<div>
			Total recipes : {recipePage.totalCount}, offset : {recipePage.offset},
			limit : {recipePage.limit}
		</div>
	{/if}
</div>

<style>
	.recipes {
		text-align: left;
	}
</style>
