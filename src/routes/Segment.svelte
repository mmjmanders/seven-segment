<script lang="ts">
	import Number from './Number.svelte';

	let entered = $state<number | undefined>(undefined);
	let normalized = $derived.by(() =>
		entered != undefined ? Math.floor(entered / (entered >= 10 ? 10 : 1)) : undefined
	);
</script>

<div class="flex flex-col gap-y-8">
	<input
		bind:value={entered}
		type="number"
		inputmode="numeric"
		min="0"
		max="9"
		class="p-2 border border-neutral-400 rounded-md outline-none focus:outline-1 focus:outline-sky-400 focus:border-sky-400 focus:outline-double"
	/>
	<Number input={normalized} />
</div>
