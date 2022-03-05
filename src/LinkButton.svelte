<script>
export let secondary;
export let href;
</script>

<style>
a {
  padding: 10px;
  border: none;
  font: inherit;
  color: white;
  background-color: #6558f5;
  cursor: pointer;
  border-radius: 3px;
  display: inline-block;
}
a:active {
	background-color: #6558f5;
}
a.secondary{
  background-color: transparent;
  color: #6558f5;
  border: 1px solid #6558f5;
}
a:hover{
  text-decoration: none;
}
</style>

<a on:click class:secondary {href}>
<slot>

</slot>
</a>


