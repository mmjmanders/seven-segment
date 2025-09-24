<script lang="ts">
	import Number from './Number.svelte';

	let entered = $state<number | undefined>(undefined);
	let nrSegments = $state<'7' | '14'>('7');
</script>

<div class="flex flex-col gap-y-8">
	<select bind:value={nrSegments} class="p-2 border border-neutral-400 rounded-md">
		<option value="7">7</option>
		<option value="14">14</option>
	</select>
	<input
		bind:value={entered}
		type="number"
		inputmode="numeric"
		min="0"
		max="9"
		class="p-2 border border-neutral-400 rounded-md outline-none focus:outline-1 focus:outline-sky-400 focus:border-sky-400 focus:outline-double"
	/>
	<Number
		input={entered != undefined ? Math.floor(entered / (entered >= 10 ? 10 : 1)) : undefined}
		nrSegments={parseInt(nrSegments, 10)}
	/>
</div>
