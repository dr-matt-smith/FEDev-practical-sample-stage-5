<script>
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
    import Footer from "$lib/components/Footer.svelte";
    import Nav from "$lib/components/Nav.svelte";
    import Header from "$lib/components/Header.svelte";

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<Header />
<Nav />

{@render children()}

<Footer />

<style>
     :global(body) {
         background: url("/images/background.png") no-repeat center center fixed;
         background-size: cover;

         color: white;
         background-color: #a07a21;
     }
</style>
