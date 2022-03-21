<script>
    import RecipeList from "./RecipeList.svelte";

    export let getRecipes;
</script>

{#if getRecipes}
    <RecipeList getRecipesFunc={getRecipes} />
{:else}
    not logged in
{/if}
