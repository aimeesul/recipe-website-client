<script>
    import { params } from "@roxi/routify";

    async function sendCreds(creds) {
        const response = await fetch("http://localhost:3000/creds", {
            headers: {
                //Authorization: "aimeeiscool",
                "Content-Type": "application/json",
            },
            method: "POST",
            body: JSON.stringify(creds),
        });

        const data = await response.json();
        console.log(data);
    }

    let code;
    let scope;
    let authuser;
    let prompt;
    $: {
        console.log("a");
        code = $params.code;
        scope = $params.scope;
        authuser = $params.authuser;
        prompt = $params.prompt;
        sendCreds({ code, scope, authuser, prompt });
    }
</script>

<div>{code}</div>
<div>{scope}</div>
<div>{authuser}</div>
<div>{prompt}</div>
