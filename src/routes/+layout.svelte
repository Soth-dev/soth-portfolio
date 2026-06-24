<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="relative min-h-screen overflow-hidden bg-slate-950 text-white">
	<!-- Atmospheric Fog Effects -->
	<div class="pointer-events-none fixed inset-0 z-0">
		<div
			class="absolute top-[10%] left-[10%] h-[40%] w-[40%] rounded-full bg-blue-500/10 blur-[120px]"
		></div>
		<div
			class="absolute top-[20%] right-[10%] h-[50%] w-[50%] rounded-full bg-purple-500/10 blur-[150px]"
		></div>
		<div
			class="absolute bottom-[20%] left-[20%] h-[60%] w-[60%] rounded-full bg-indigo-500/15 blur-[180px]"
		></div>

		<!-- Ground Fog -->
		<div
			class="absolute bottom-0 h-64 w-full bg-linear-to-t from-slate-950 via-slate-950/40 to-transparent backdrop-blur-[1px]"
		></div>
	</div>

	<!-- iOS-style Top Shadow/Gradient -->
	<div
		class="pointer-events-none fixed inset-x-0 top-0 z-40 h-32 bg-linear-to-b from-black/40 to-transparent"
	></div>

	<!-- Header at the top -->
	<div class="relative z-50 flex justify-center p-4">
		<Header />
	</div>

	<!-- Main content -->
	<main class="relative z-20 min-h-screen w-full px-4 pt-4 pb-32">
		<div class="mx-auto max-w-6xl">
			{@render children()}
		</div>
	</main>

	<!-- Footer fixed at the bottom - lowered to bottom-4 -->
	<div class="fixed bottom-4 right-0 left-0 z-50 flex justify-center px-4">
		<Footer />
	</div>
</div>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		background-color: #020617; /* slate-950 */
	}
</style>
