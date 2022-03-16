<script>
    import RecipeList from "./RecipeList.svelte";

    let recipePage = undefined;

    fetch("http://localhost:3000/recipes", {
        headers: { Authorization: "aimeeiscool" },
    })
        .then((response) => response.json())
        .then((data) => {
            recipePage = data;
        });
</script>

<RecipeList {recipePage} />
