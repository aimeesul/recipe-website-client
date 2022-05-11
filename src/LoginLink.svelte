<script>
    import { user } from "./stores";
    import { accessToken } from "./stores";
    import LinkButton from "./LinkButton.svelte";
    import { url } from "@roxi/routify";
    import Button from "./Button.svelte";

    function logout(event) {
        user.set(null);
        accessToken.set(null);
        event.preventDefault();
    }
</script>

{#if $user}
    <div>logged in as {$user.userName}</div>
    <div>
        <LinkButton secondary href={$url("/recipes/addNew")}
            >Add new recipe</LinkButton
        >
        <LinkButton secondary href="http://localhost:3000/api/authentication/google/start" 
            >Switch account</LinkButton
        >
        <LinkButton secondary href="http://localhost:5000" on:click={logout}
            >Log out</LinkButton
        >
    </div>
{:else}
    <a href="http://localhost:3000/api/authentication/google/start"
        >Log in with Google</a
    >
{/if}
