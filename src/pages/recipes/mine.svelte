<script>
    import { url } from "@roxi/routify";
    import LinkButton from "../../LinkButton.svelte";
    import RecipeDisplay from "../../RecipeDisplay.svelte";
</script>

<LinkButton secondary href={$url("./addNew")}>Add new recipe</LinkButton>


<RecipeDisplay />
