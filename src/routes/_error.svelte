<script>
	export let status;
	export let error;

	const dev = process.env.NODE_ENV === 'development';
</script>

<style>
	.container {
		min-height: 75vh;
	}
</style>

<svelte:head>
	<title>{status}</title>
</svelte:head>

<div class="container mx-auto text-center text-gray-600 flex flex-col justify-center">
	<h1 class="text-5xl">{ status }</h1>

	<p class="text-lg">{ error.message }</p>

	{#if dev && error.stack}
		<pre>{ error.stack }</pre>
	{/if}
</div>
