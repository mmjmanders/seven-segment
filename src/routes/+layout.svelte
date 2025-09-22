<script lang="ts">
	import '@fontsource-variable/roboto';
	import '@fontsource-variable/roboto-mono';
	import '../styles.css';
	import { asset } from '$app/paths';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={asset('/favicon.svg')} />
	<link rel="apple-touch-icon" href={asset('/apple-touch-icon.png')} />
	<link rel="manifest" href={asset('/site.webmanifest')} />
</svelte:head>

{@render children?.()}
