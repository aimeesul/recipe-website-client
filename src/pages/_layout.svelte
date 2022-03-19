<script>
    import Banner from "../Banner.svelte";
</script>

<header><Banner /></header>

<main><slot /></main>

<style>
    main {
        text-align: center;
        padding: 0 1em 1em 1em;
    }
    /* @media (min-width: 640px) {
        main {
            max-width: none;
        }
    } */
</style>
