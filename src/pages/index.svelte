<script>
    import RecipeList from "../RecipeList.svelte";
    export let name;

    let recipePage = undefined;

    fetch("http://localhost:3000/recipes", {
        headers: { Authorization: "aimeeiscool" },
    })
        .then((response) => response.json())
        .then((data) => {
            recipePage = data;
        });
</script>


<h1>Hello000000 {name}!</h1>
<p>
    Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
    how to build Svelte apps.
</p>
<RecipeList {recipePage} />

<style>
    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    
</style>
