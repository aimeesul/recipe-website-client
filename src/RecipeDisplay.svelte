<script>
    import RecipeList from "./RecipeList.svelte";

    async function getRecipes(offset, limit) {
        const response = await fetch(
            `http://localhost:3000/recipes?limit=${limit}&offset=${offset}`,
            {
               // headers: { Authorization: "aimeeiscool" },
            }
        );
        const data = await response.json();
        return data;
        // .then((response) => response.json())
        // .then((data) => {
        //     recipePage = data;
        // });
    }
</script>

<RecipeList getRecipesFunc={getRecipes} />
