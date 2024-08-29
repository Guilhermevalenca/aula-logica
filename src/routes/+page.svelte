<script lang="ts">
	class Coordenada {
		linha: number;
		coluna: number;
	}
	const jogador = new Coordenada();
	jogador.linha = 0;
	jogador.coluna = 2;

	const mapa: number[][] = [
		[0,0,0,0],
		[0,0,0,0],
		[0,0,0,0],
	];
	function keydown(event: KeyboardEvent) {
		if(event.key === 'w') {
			jogador.linha--;
		} else if(event.key === 's') {
			jogador.linha++;
		} else if(event.key === 'd') {
			jogador.coluna++;
		} else if(event.key === 'a') {
			jogador.coluna--;
		}
	}
</script>
<svelte:window on:keydown={keydown} />
<table>
	{#each mapa as linhas, i}
	<tr
		style="display: flex;"
	>
		{#each linhas as colunas, j}
			{#if jogador.coluna === j && jogador.linha === i}
				<td
					style="width: 16px; height: 16px;
					background-color: black;"
				></td>
			{:else}
				<td
					style="width: 16px; height: 16px;background-color: aqua"
				></td>
			{/if}
		{/each}
	</tr>
	{/each}
</table>