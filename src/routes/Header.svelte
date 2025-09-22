<script lang="ts">
	const { VITE_APP_VERSION, VITE_BUILD_SHA } = import.meta.env;
</script>

<header class="relative">
	<h1 class="h1 text-5xl font-medium">Segment</h1>
	<span class="absolute font-mono text-xs right-0">v{VITE_APP_VERSION} - {VITE_BUILD_SHA}</span>
</header>
