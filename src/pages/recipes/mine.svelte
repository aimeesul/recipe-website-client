<script>
    import RecipeDisplay from "../../RecipeDisplay.svelte";
    import { accessToken } from "../../stores";

    async function getRecipes(offset, limit) {
        if ($accessToken == null) {
            return undefined;
        }
        const response = await fetch(
            `http://localhost:3000/recipes/mine?limit=${limit}&offset=${offset}`,
            {
                headers: { Authorization: "JWT " + $accessToken },
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

<RecipeDisplay getRecipes={$accessToken ? getRecipes : undefined} />
