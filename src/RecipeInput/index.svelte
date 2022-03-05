<script>
    import Button from "../Button.svelte";
    let measurementUnits = undefined;

    fetch("http://localhost:3000/measurementUnits", {
        headers: { Authorization: "aimeeiscool" },
    })
        .then((response) => response.json())
        .then((data) => {
            measurementUnits = data;
        });

    let ingredients = [];
    let name = "";
    let quantity = 1;
    let measurment = "item";

    function addIngredient() {
        ingredients[ingredients.length] = { name, quantity, measurment };
        name = "";
        quantity = 1;
    }
</script>

<div>
    {#each ingredients as ingredient}
        <div>
            <input type="text" bind:value={ingredient.name} readonly />
            <input
                type="number"
                bind:value={ingredient.quantity}
                readonly
            />
        </div>
    {/each}
    <div>
        <input type="text" bind:value={name} />
        <input type="number" bind:value={quantity} />
        <Button on:click={addIngredient}>Add</Button>
    </div>
</div>

{#if measurementUnits!=null}
    {#each measurementUnits as measurementUnit}
        <div>
            {measurementUnit.unitName}
        </div>
    {/each}
{/if}
