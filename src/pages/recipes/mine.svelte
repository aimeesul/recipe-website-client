<script>
    import { url } from "@roxi/routify";
    import LinkButton from "../../LinkButton.svelte"
</script>

<LinkButton secondary href={$url("./addNew")}>
    Add new recipe
</LinkButton>