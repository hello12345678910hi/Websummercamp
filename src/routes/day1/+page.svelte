<script>
	import Button from '../../components/button.svelte';
</script>

<div class="w-full bg-blue-300">
	<div class="prose p-5">
		<h1 class="text-center">Vincent's Profile</h1>

		<hr />

		<div
			class="profile-image h-20 w-20 overflow-hidden rounded-full bg-black bg-cover bg-center"
		></div>
		<div>Vincent Dang</div>

		<h2>About Me</h2>

		<p>Hi my name is Vincent.</p>

		<h2 class="bg-blue-400 text-center">Haikus are funny</h2>
		<h2 class="bg-green-400 text-center">I can't think of any now</h2>
		<h2 class="bg-blue-100 text-center">Help what do I say</h2>

		<h2>Components</h2>

		<Button text={'CLICK ME'} message={'I was clicked'} />
		<Button text={'DONT CLICK ME'} message={'why did you click me when i said no :c'} />
	</div>
</div>

<style>
	.profile-image {
		background-image: url('https://images.unsplash.com/photo-1754196668084-aad13474e6f2?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHwzNHx8fGVufDB8fHx8fA%3D%3D');
	}
</style>
