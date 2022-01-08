<script>
	export let recipeIngredient;
</script>

<div>
	{recipeIngredient.quantity}
	{#if recipeIngredient.measurementUnit != null}
		{recipeIngredient.measurementUnit.unitName}
	{/if}

	{recipeIngredient.ingredient.ingredientName}

</div>
