<script>
    import { url, isActive } from "@roxi/routify";
    export let path;
</script>

<div class="navmenuitem" class:active={$isActive(path)}><a href={$url(path)}><slot /></a></div>

<style>
    .navmenuitem {
        border-bottom: 3px solid transparent;
        flex-grow: 1;
        padding-bottom: 5px;
    }
    .active {
        border-bottom: 3px solid black;
    }
    a:active,a:hover{
        text-decoration: none;
    }
</style>
