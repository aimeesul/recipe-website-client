<script>
    import RecipeDisplay from "../RecipeDisplay.svelte";

    async function getRecipes(offset, limit) {
        const response = await fetch(
            `http://localhost:3000/recipes?limit=${limit}&offset=${offset}`
        );
        const data = await response.json();
        return data;
        // .then((response) => response.json())
        // .then((data) => {
        //     recipePage = data;
        // });
    }
</script>

<h1>Recipe Share</h1>

<RecipeDisplay {getRecipes} />

<style>
    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }
</style>
