<script>
    import Recipe from "../../Recipe.svelte";
    export let recipeId;
    let recipe = undefined;
    fetch("http://localhost:3000/recipe/" + recipeId, {
      //  headers: { Authorization: "aimeeiscool" },
    })
        .then((response) => response.json())
        .then((data) => {
            console.log(data);
            recipe = data;
        });
</script>

{#if recipe != null}
    <Recipe {recipe} />
{:else}
    loading
{/if}
