<script>
	let CPSNumber = 0;
	let amount = 10;
</script>

<body>
	<div class="mainer">
	<header>
		<h1>Your clicks: <strong>{CPSNumber}</strong></h1>
	</header>
	
	<main>
		{#if CPSNumber >= amount}
			<h1>You have {CPSNumber} CPS</h1>
		{/if}	
		{#if CPSNumber <= amount - 1}
			<div class="btn">
				<button on:click={() => CPSNumber++}>Click me</button>
			</div>
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
		margin: 5em 8em;
		background: white;
		border-radius: 25px;
		padding: 1.5em;
	}

</style>