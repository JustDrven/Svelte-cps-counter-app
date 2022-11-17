<script>
	let CPSNumber = 0;
	let amount = 10;
	let showIng = false;

	let clicking = true;

	$: if(CPSNumber == amount) {
		clicking = false;
		showIng = true;
	} else {
		clicking = true;
		showIng = false;
	}

</script>

<body>
	<div class="mainer">
	<header>

		{#if showIng == true}
			<h1><strong>The End</strong></h1>
		{/if}

		{#if clicking == true}
			<h1>Your clicks: <strong>{CPSNumber}</strong></h1>
		{/if}
		
	</header>
	
	<main>

		{#if CPSNumber >= amount}
			<h1>You have <strong>{CPSNumber}</strong> CPS</h1>
		{/if}	
		{#if CPSNumber <= amount - 1}
			<div class="btn">
				<button on:click={() => CPSNumber++}>Click me</button>
			</div>
			{:else if  CPSNumber >= amount - 1}
			<form action="">
				<button class="btned">Restart</button>
			</form>
		{/if}
		

	</main>
	</div>
		
</body>

<style>

	* {
		text-align: center;
	}

	.btn button {
		color: rgb(255, 255, 255);
		background: rgb(230, 83, 83);
		border-radius: 12px;
		padding: 1.9em 3em;
		font-weight: bold;
		font-size: 0.8em;
		text-transform: uppercase;
		border: 0;
		outline: none;
		cursor: pointer;
	}

	.mainer {
		margin: 10rem auto;
		background: white;
		border-radius: 25px;
		padding: 1.5em;
		width: clamp(18rem, 42vw, 42rem);
	}


	strong {
		color: rgb(230, 83, 83);
	}

	.btned {
		color: rgb(255, 255, 255);
		background: rgb(230, 83, 83);
		border-radius: 12px;
		padding: 1.9em 3em;
		font-weight: bold;
		font-size: 0.8em;
		text-transform: uppercase;
		border: 0;
		outline: none;
		cursor: pointer;
	}

</style>