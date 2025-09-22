<script lang="ts">
	import '@fontsource-variable/roboto';
	import '@fontsource-variable/roboto-mono';
	import '../styles.css';
	import favicon from '$lib/assets/favicon.svg';
	import appleTouchIcon from '$lib/assets/apple-touch-icon.png';
	import { asset } from '$app/paths';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<link rel="apple-touch-icon" href={appleTouchIcon} />
	<link rel="manifest" href={asset('/site.webmanifest')} />
</svelte:head>

{@render children?.()}
