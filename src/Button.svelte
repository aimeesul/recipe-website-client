<script>
export let type;
export let secondary;
</script>

<style>
button {
  padding: 10px;
  border: none;
  font: inherit;
  color: white;
  background-color: #6558f5;
  cursor: pointer;
  border-radius: 3px;
}
button:active {
	background-color: #6558f5;
}
button.secondary{
  background-color: transparent;
  color: #6558f5;
  border: 1px solid #6558f5;
}
</style>

<button on:click {type} class:secondary>
<slot>

</slot>
</button>


