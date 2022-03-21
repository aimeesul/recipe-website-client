<script>
    import { user } from "./stores";
    import LinkButton from "./LinkButton.svelte";
    import { url } from "@roxi/routify";
</script>

{#if $user}
    <div>logged in as {$user.userName}</div>
    <div>
        <LinkButton secondary href={$url("/recipes/addNew")}>Add new recipe</LinkButton
        >
    </div>
{:else}
    <a href="http://localhost:3000/api/authentication/google/start"
        >Log in with Google</a
    >
{/if}
