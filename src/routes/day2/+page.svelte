<script>
	import Button from '../../components/button.svelte';
	import LoadingBar from '../../components/LoadingBar.svelte';
	import HorseRace from './HorseRace.svelte';
	let progress = $state(10);

	function increment() {
		progress += 10;
		if (progress > 100) {
			progress = 100;
		}
	}

	function decrement() {
		progress -= 10;
		if (progress < 0) {
			progress = 0;
		}
	}

	function reset() {
		progress = 0;
	}
</script>

<HorseRace />

<div class="bg-red-500 text-center transition-all duration-1000 hover:bg-blue-500">Transition</div>

<div
	class="hover:rotate-1080hover:bg-green-500 m-2 h-10 w-10 border bg-red-500 transition-all duration-1000 hover:translate-x-96"
>
	Box 1
</div>
<div
	class="m-2 h-10 w-10 border bg-cyan-300 transition-all duration-1000 hover:w-100 hover:bg-purple-500"
>
	Box 2
</div>
<div
	class="m-2 h-10 w-10 border bg-orange-500 transition-all duration-1000 hover:border-r-8 hover:bg-blue-500 hover:text-gray-200 hover:backdrop-blur-xl"
>
	Box 3
</div>
<div
	class="bg-brown-500 m-2 h-10 w-10 border transition-all duration-1000 hover:h-123 hover:w-100 hover:bg-yellow-500 hover:text-gray-200"
>
	Box 4
</div>
<Button text={'Increment'} fn={increment} />
<Button text={'Decrement'} fn={decrement} />
<Button text={'Reset'} fn={reset} />
<LoadingBar color={'bg-blue-500'} current={progress} max={100} />
