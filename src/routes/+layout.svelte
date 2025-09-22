<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import { asset } from '$app/paths';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<link rel="apple-touch-icon" href={asset('/apple-touch-icon.png')} />
	<link rel="manifest" href={asset('/site.webmanifest')} />
</svelte:head>

{@render children?.()}
