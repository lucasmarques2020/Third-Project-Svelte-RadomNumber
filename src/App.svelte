<script>
	let cursos = ['html', 'css', 'js']
	let numeros = []
	let cont = 5

	const agregarNumero = ()=>{
		let num = Math.floor(Math.random()*(200 - 1))+1;
		console.log(num)
		numeros = [...numeros, num]
		cont--
	}
	const reiniciarN = ()=>{
		numeros = []
		cont = 5
	}
	
</script>

<main class="container">
	<h2>Clique para gerar 5 números aleatórios</h2>
	
	<ul>
		{#each numeros as numero}
			<li>{numero}</li>
		{/each}

		{#if numeros.length >= 5}
			<h3>Obrigado por clicar!</h3>
			<button on:click={reiniciarN}>Reiniciar</button>
			{:else}
			<button on:click={agregarNumero}>Clique aqui! {cont}</button>
			
		{/if}
	</ul>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
	li{
		list-style: none;
	}
	h2 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 2em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>