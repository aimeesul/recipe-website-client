<script>
    import Button from "../Button.svelte";
    import Select from "svelte-select";
    let measurementUnits = undefined;

    fetch("http://localhost:3000/measurementUnits", {
      //  headers: { Authorization: "aimeeiscool" },
    })
        .then((response) => response.json())
        .then((data) => {
            measurementUnits = data;
        });

    let ingredients = [];
    let name = "";
    let quantity = 1;
    let measurement = undefined;

    function addIngredient(event) {
        ingredients[ingredients.length] = { name, quantity, measurement };
        name = "";
        quantity = 1;
        measurement = undefined;
        event.preventDefault();
    }

    let steps = [];
    let step = "";
    function addStep(event) {
        steps[steps.length] = step;
        step = "";
        event.preventDefault();
    }

    let title="";

    async function postRecipe() {
        const recipe = { title, steps, ingredients };
        console.log(recipe);

        const sentOk = await sendRecipe(recipe);
        if (sentOk) {
            steps = [];
            ingredients = [];
            title = "";
        }
    }
    async function sendRecipe(recipe) {
        const response = await fetch("http://localhost:3000/recipes", {
            headers: {
                //Authorization: "aimeeiscool",
                "Content-Type": "application/json",
            },
            method: "PUT",
            body: JSON.stringify(recipe),
        });
        return response.ok;
    }
</script>

{#if measurementUnits != null}
    <div class="title">
        <label>Title of recipe: <input type="text" bind:value={title} /></label>
        
    </div>
    <div class="ingredients">
        <div> Please input ingredients below:</div>
        {#each ingredients as ingredient}
            <div>
                <span>{ingredient.name}</span>
                <span>{ingredient.quantity}</span>
                <span>{ingredient.measurement.unitName}</span>
            </div>
        {/each}
        <form class="inputs">
            <input type="text" bind:value={name} /> 
            <input type="number" bind:value={quantity} />
            <div class="selectContainer">
                <Select
                    items={measurementUnits}
                    optionIdentifier="id"
                    labelIdentifier="unitName"
                    on:select={(event) => {
                        measurement = event.detail;
                        if (
                            !measurementUnits.some(
                                (mu) => mu.unitName === event.detail.unitName
                            )
                        ) {
                            measurementUnits[measurementUnits.length] =
                                event.detail;
                        }
                    }}
                    bind:value={measurement}
                    isCreatable
                    createItem={(text) => ({ value: null, unitName: text })}
                />
            </div>

            <Button on:click={addIngredient}>Add</Button>
        </form>
    </div>
    <div class="steps">
        <div>Please input method below:</div>
        {#each steps as step}
            <div>
                <span>{step}</span>
            </div>
        {/each}
        <form class="stepsInput">
            <input type="text" bind:value={step} />
            <Button on:click={addStep}>Add</Button>
        </form>
    </div>
    {#if ingredients.length > 0 && steps.length > 0 && title.length>0}
        <div>
            <Button on:click={postRecipe}>Post Recipe</Button>
        </div>
    {/if}
{:else}
    loading
{/if}

<style>
    .inputs {
        display: flex;
        flex-direction: row;
        justify-content: center;
    }
    .selectContainer {
        min-width: 10em;
    }
</style>
