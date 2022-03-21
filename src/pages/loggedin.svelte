<script>
    import { goto } from "@roxi/routify";
    import { accessToken, user } from "../stores";
    let urlHash = decodeURIComponent(window.location.hash);
    if (urlHash.startsWith("#")) {
        urlHash = urlHash.substring(1);
    }
    history.replaceState(
                "",
                document.title,
                window.location.pathname + window.location.search
            );
    try {
        const { accessToken: token } = JSON.parse(urlHash);
        console.log(token);

        accessToken.set(token);

        fetch("http://localhost:3000/api/user", {
            headers: { Authorization: "JWT " + $accessToken },
        }).then(async (r) => {
            console.log("ff",r)
            const u = await r.json();
            console.log("user",u)
            user.set(u);
            $goto("/recipes/mine");
        });
    } catch (e) {
        $goto("/recipes/mine");
    }
</script>

logged in
