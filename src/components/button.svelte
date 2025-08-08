<script>
	let { text, fn } = $props();
</script>

<button
	onclick={fn}
	class=" rounded border px-3 py-1 transition-all duration-200 hover:rotate-360 hover:bg-black hover:text-white active:scale-110"
	>{text}</button
>
