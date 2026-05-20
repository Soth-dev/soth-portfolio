<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import Header from '$lib/components/Header.svelte';

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<div class="relative min-h-screen">
	<!-- Header is fixed at the top and forced to the front layer -->
	<div class="fixed top-0 right-0 left-0 z-50 flex justify-center p-4">
		<Header />
	</div>

	<!-- Main content now starts at the absolute top of the screen under the header -->
	<main class="min-h-screen w-full pt-24">
		{@render children()}
	</main>
</div>
