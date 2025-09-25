<script lang="ts">
	let { input, nrSegments }: { input: number | undefined; nrSegments: number } = $props();
	const masks: { [key: number]: { [key: number]: number } } = {
		7: {
			0: 0b1111110,
			1: 0b0110000,
			2: 0b1101101,
			3: 0b1111001,
			4: 0b0110011,
			5: 0b1011011,
			6: 0b1011111,
			7: 0b1110000,
			8: 0b1111111,
			9: 0b1111011
		},
		14: {
			0: 0b11111100100010,
			1: 0b01100000100000,
			2: 0b11011000010001,
			3: 0b11110000010000,
			4: 0b01100100010001,
			5: 0b10110100010001,
			6: 0b10111100010001,
			7: 0b10000000100100,
			8: 0b11111100010001,
			9: 0b11110100010001
		}
	};

	const state: (i: number) => 'on' | 'off' = (i) => {
		if (input == undefined) {
			return 'off';
		}
		return ((1 << (nrSegments - 1 - i)) & masks[nrSegments][input]) != 0 ? 'on' : 'off';
	};
</script>

{#if nrSegments === 14}
	<svg viewBox="0 0 143 202.25" class="svg-background">
		<g transform="translate(-62.5,-639.1875)" stroke-linecap="square">
			<path
				class="stroke-current stroke-2 {state(0)}"
				d="m 84.047405,640.28548 99.809675,-0.067 10,10 -10,10 -99.809675,0.067 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(1)}"
				d="m 184.29713,730.19264 0,-70 10,-10 10,10 0,70 -10,10 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(2)}"
				d="m 184.29713,820.1926 0,-70 10,-10 10,10 0,70 -10,10 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(3)}"
				d="m 84.047405,820.4512 99.809675,-0.067 10,10 -10,10 -99.809675,0.067 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(4)}"
				d="m 64.297129,820.1926 0,-70 10,-10 10,10 0,70 -10,10 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(5)}"
				d="m 64.297129,730.19264 0,-70 10,-10 10,10 0,70 -10,10 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(6)}"
				d="m 94.297079,660.19268 30,50 0,20 -10,0 -30,-50 0,-20 10,0 z"
			/>
			<path
				class="stroke-current stroke-2 {state(7)}"
				d="m 124.29713,730.19264 0,-70 10,-10 10,10 0,70 -10,10 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(8)}"
				d="m 174.29708,660.19268 -30,50 0,20 10,0 30,-50 0,-20 -10,0 z"
			/>
			<path
				class="stroke-current stroke-2 {state(9)}"
				d="m 144.29713,730.19264 40,0 10,10 -10,10 -40,0 -10,-10 10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(10)}"
				d="m 174.29708,820.1927 -30,-50 0,-20 10,0 30,50 0,20 -10,0 z"
			/>
			<path
				class="stroke-current stroke-2 {state(11)}"
				d="m 124.29713,820.1926 0,-70 10,-10 10,10 0,70 -10,10 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(12)}"
				d="m 94.297079,820.1927 30,-50 0,-20 -10,0 -30,50 0,20 10,0 z"
			/>
			<path
				class="stroke-current stroke-2 {state(13)}"
				d="m 84.297129,730.19264 40,0 10,10 -10,10 -40,0 -10,-10 10,-10 z"
			/>
		</g>
	</svg>
{:else}
	<svg viewBox="0 0 143 202.25" class="svg-background">
		<g transform="translate(279.53125,-639.1875)" stroke-linecap="square">
			<path
				class="stroke-current stroke-2 {state(0)}"
				d="m -258.34868,640.28548 99.80967,-0.067 10,10 -10,10 -99.80967,0.067 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(1)}"
				d="m -158.53902,730.19264 0,-70 10,-10 10,10 0,70 -10,10 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(2)}"
				d="m -158.53902,820.1926 0,-70 10,-10 10,10 0,70 -10,10 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(3)}"
				d="m -258.34868,820.2596 99.80967,-0.067 10,10 -10,10 -99.80967,0.067 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(4)}"
				d="m -278.53901,820.1926 0,-70 10,-10 10,10 0,70 -10,10 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(5)}"
				d="m -278.53901,730.19264 0,-70 10,-10 10,10 0,70 -10,10 -10,-10 z"
			/>
			<path
				class="stroke-current stroke-2 {state(6)}"
				d="m -258.34868,730.60039 99.80967,-0.067 10,10 -10,10 -99.80967,0.067 -10,-10 z"
			/>
		</g>
	</svg>
{/if}

<style lang="scss">
	.svg-background {
		color: var(--color-neutral-50);

		@media (prefers-color-scheme: dark) {
			color: var(--color-neutral-900);
		}
	}

	.off {
		fill: var(--color-neutral-400);
		fill-opacity: 0.25;

		@media (prefers-color-scheme: dark) {
			fill: var(--color-neutral-100);
		}
	}

	.on {
		fill: var(--color-red-600);

		@media (prefers-color-scheme: dark) {
			fill: var(--color-red-400);
		}
	}
</style>
