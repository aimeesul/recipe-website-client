<script>
    import NavmenuItem from "./NavmenuItem.svelte";
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
