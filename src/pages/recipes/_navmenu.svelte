<script>
    import { url } from "@roxi/routify";
    import NavmenuItem from "./_navmenuItem.svelte";
</script>

<div class="navmenu">
    <NavmenuItem path={"./index"}>Hottest Recipes</NavmenuItem><NavmenuItem
        path={"./saved"}>Saved Recipes</NavmenuItem
    ><NavmenuItem path={"./mine"}>My Recipes</NavmenuItem>
</div>

<style>
    .navmenu {
        display: flex;
        flex-direction: row;
        justify-content: space-evenly;
    }
</style>
