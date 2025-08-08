<script>
	import { onMount } from 'svelte';
	import Button from '../../components/button.svelte';
	import { passive } from 'svelte/legacy';

	let points = $state(0);
	let clickingPower = $state(1);
	let passiveIncome = $state(1);

	let upgradeClickingCost = 10;
	let upgradePassiveCost = 50;

	onMount(() => {
		// interval
		let passiveTimer = setInterval(() => {
			points += passiveIncome;
		}, 1000);

		return () => clearInterval(passiveTimer);
	});

	function increment() {
		points += clickingPower;
	}

	function upgradeClickingPower(amount) {
		if (points - amount * upgradeClickingCost >= 0) {
			points -= amount * upgradeClickingCost;
			clickingPower += amount;
		}
	}

	function upgradePassiveIncome(amount) {
		if (points - amount * upgradePassiveCost >= 0) {
			points -= amount * upgradePassiveCost;
			clickingPower += amount;

			if (amount >= 1000000) {
				alert('go touch grass');
			}
		}
	}
</script>

<!--container for the game-->
<div
	class="from-aqua-300 flex h-screen flex-col items-center justify-center bg-blue-200 bg-gradient-to-b via-blue-700"
>
	<div>{points}</div>
	<button
		onclick={increment}
		class="h-48 w-48 rounded-full bg-blue-900 transition-all duration-115 active:scale-110"
	></button>
	<div class="flex w-full flex-col border">
		<div class="w-1/2"></div>
		<div>Click Upgrades</div>
		<Button text="+1 - {1 * upgradeClickingCost}" fn={() => upgradeClickingPower(1)}></Button>
		<Button text="+5 - {5 * upgradeClickingCost}" fn={() => upgradeClickingPower(5)}></Button>
		<Button text="+123 {123 * upgradeClickingCost}" fn={() => upgradeClickingPower(123)}></Button>
		<Button text="+5040 {5040 * upgradeClickingCost}" fn={() => upgradeClickingPower(5040)}
		></Button>
		<div class="w-1/2"></div>
		<div>Passive Upgrades</div>
		<Button text={'+1 - 400'} fn={() => upgradePassiveIncome(1)}></Button>
	</div>
</div>

<Button text={'+1'} fn="{increment}}"></Button>
