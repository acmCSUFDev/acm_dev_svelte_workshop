<script>
	let cookies = 0;
	let cookiesPerSecond = 0;
	function addOne() {
		cookies++;
	}
	setInterval(() => {
		cookies += cookiesPerSecond / 100;
	}, 10);

	/**
	 * @param {number} price
	 * @param {number} upgradeValue
	 */
	function buyUpgrade(price, upgradeValue) {
		cookies -= price;
		cookiesPerSecond += upgradeValue;
	}
</script>

<div class="center">
	<h1>Karni's Bakery: {Math.round(cookies)} cookies</h1>
	<h2>Cookies per second: {cookiesPerSecond}</h2>
	<button on:click={addOne}>Bake 1</button>
	<div class="center">
		Upgrades
		<div class="upgrades">
			<div class="center">
				Goat Labor (-10 cookies)
				{#if cookies > 10}
					<button
						on:click={() => {
							buyUpgrade(10, 10);
						}}>Buy</button
					>
				{:else}
					<button disabled>Buy</button>
				{/if}
			</div>
			<div class="center">
				Hydrogen Powered Oven (-20 cookies)
				{#if cookies > 20}
					<button
						on:click={() => {
							buyUpgrade(20, 20);
						}}>Buy</button
					>
				{:else}
					<button disabled>Buy</button>
				{/if}
			</div>
			<div class="center">
				Vim download (+30 cookies)
				{#if cookies > 30}
					<button
						on:click={() => {
							buyUpgrade(30, 30);
						}}>Buy</button
					>
				{:else}
					<button disabled>Buy</button>
				{/if}
			</div>
			<div class="center">
				Wifi Upgrade (-40 Cookies)
				{#if cookies > 40}
					<button
						on:click={() => {
							buyUpgrade(40, 40);
						}}>Buy</button
					>
				{:else}
					<button disabled>Buy</button>
				{/if}
			</div>

            <div class="center">
				SHALEEN (100 cookies)
				{#if cookies > 100}
					<button
						on:click={() => {
							buyUpgrade(100, -100);
						}}>Buy</button
					>
				{:else}
					<button disabled>Buy</button>
				{/if}
			</div>
		</div>
	</div>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
	/* https://coolors.co/048a81-06d6a0-65afff-cda2ab-e15554 */
	* {
		font-family: 'Poppins', sans-serif;
	}
	div {
		border: 1px solid #e15554;
	}
	.upgrades {
		display: flex;
	}
	.center {
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
	}
	.wrapper {
		display: flex;
	}
</style>
