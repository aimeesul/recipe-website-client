<script>
    import Banner from "../Banner.svelte";
    import LoginLink from "../LoginLink.svelte";
</script>

<header><Banner><LoginLink></LoginLink></Banner></header>

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
