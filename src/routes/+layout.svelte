<script>
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>
{@render children()}

<style>
     :global(body) {
         background: url("/images/background.png") no-repeat center center fixed;
         background-size: cover;

         color: white;
         background-color: #a07a21;
     }
</style>
