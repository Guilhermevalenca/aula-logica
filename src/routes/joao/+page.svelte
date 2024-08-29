<script lang="ts">
	let escrevendo: string = '';
</script>

<h1 style="background-color: {escrevendo === 'ola' ? 'aqua' : 'red'};">{escrevendo}</h1>

<input bind:value={escrevendo} >