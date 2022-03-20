<script>
    let loginUrl = undefined;
    fetch("http://localhost:3000/loginUrl")
        .then((r) => r.json())
        .then((data) => {
            loginUrl = data.url;
        });
</script>

{#if loginUrl != null}
    <a href={loginUrl}>Log in with Google</a>
{/if}
