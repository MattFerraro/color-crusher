<script>
	import chroma from 'chroma-js';

	let numColors = 9;
	let mode = 'oklab';

	let allModes = ['rgb', 'hsl', 'hsv', 'lab', 'lch', 'oklab', 'oklch'];

	// let colors = ['#FF2E00', '#FEA82F', '#56D25B', '#0088CB', '#5448C8', '#66788E', '#808080'];

	let color1 = '#FF2E00';
	$: scale1 = chroma.valid(color1)
		? chroma
				.scale(['#fff', color1, '#000'])
				.mode(mode)
				.colors(numColors + 2)
				.slice(1, -1)
		: [];
	let color2 = '#FEA82F';
	$: scale2 = chroma.valid(color2)
		? chroma
				.scale(['#fff', color2, '#000'])
				.mode(mode)
				.colors(numColors + 2)
				.slice(1, -1)
		: [];
	let color3 = '#56D25B';
	$: scale3 = chroma.valid(color3)
		? chroma
				.scale(['#fff', color3, '#000'])
				.mode(mode)
				.colors(numColors + 2)
				.slice(1, -1)
		: [];
	let color4 = '#0088CB';
	$: scale4 = chroma.valid(color4)
		? chroma
				.scale(['#fff', color4, '#000'])
				.mode(mode)
				.colors(numColors + 2)
				.slice(1, -1)
		: [];
	let color5 = '#5448C8';
	$: scale5 = chroma.valid(color5)
		? chroma
				.scale(['#fff', color5, '#000'])
				.mode(mode)
				.colors(numColors + 2)
				.slice(1, -1)
		: [];
	let color6 = '#66788E';
	$: scale6 = chroma.valid(color6)
		? chroma
				.scale(['#fff', color6, '#000'])
				.mode(mode)
				.colors(numColors + 2)
				.slice(1, -1)
		: [];
	let color7 = '#808080';
	$: scale7 = chroma.valid(color7)
		? chroma
				.scale(['#fff', color7, '#000'])
				.mode(mode)
				.colors(numColors + 2)
				.slice(1, -1)
		: [];

	// let selected = '20';

	function onChange(event) {
		mode = event.currentTarget.value;
	}
</script>

<div class="container">
	<div class="banner">
		<div>Color Crusher: A tool for making color palettes</div>
	</div>

	<div>
		{#each allModes as m}
			<label>
				<input checked={mode === m} on:change={onChange} type="radio" name="amount" value={m} />
				{m}
			</label>
		{/each}

		<!-- <label>
			<input checked={mode === 'hsl'} on:change={onChange} type="radio" name="amount" value="hsl" />
			hsl
		</label>
		<label>
			<input checked={mode === 'rgb'} on:change={onChange} type="radio" name="amount" value="rgb" />
			rgb
		</label>
		<label>
			<input checked={mode === 'hsv'} on:change={onChange} type="radio" name="amount" value="hsv" />
			hsv
		</label> -->
	</div>

	<div class="main-content">
		<div class="color-palette" style="background: {color1}">
			<input bind:value={color1} />
			{#each scale1 as color}
				<div class="swatch" style="background:{color}" />
			{/each}
		</div>
		<div class="color-palette" style="background: {color2}">
			<input bind:value={color2} />
			{#each scale2 as color}
				<div class="swatch" style="background:{color}" />
			{/each}
		</div>
		<div class="color-palette" style="background: {color3}">
			<input bind:value={color3} />
			{#each scale3 as color}
				<div class="swatch" style="background:{color}" />
			{/each}
		</div>
		<div class="color-palette" style="background: {color4}">
			<input bind:value={color4} />
			{#each scale4 as color}
				<div class="swatch" style="background:{color}" />
			{/each}
		</div>
		<div class="color-palette" style="background: {color5}">
			<input bind:value={color5} />
			{#each scale5 as color}
				<div class="swatch" style="background:{color}" />
			{/each}
		</div>
		<div class="color-palette" style="background: {color6}">
			<input bind:value={color6} />
			{#each scale6 as color}
				<div class="swatch" style="background:{color}" />
			{/each}
		</div>
		<div class="color-palette" style="background: {color7}">
			<input bind:value={color7} />
			{#each scale7 as color}
				<div class="swatch" style="background:{color}" />
			{/each}
		</div>
	</div>
</div>

<style>
	.container {
		display: flex;
		flex-direction: column;
		margin: 0px;
		padding: 0px;
	}

	.banner {
		font-size: 2rem;
		text-align: center;
		align-items: center;
		justify-content: center;
		height: 40px;
		display: flex;
		background: linear-gradient(
			90deg,
			#ffff00 0%,
			#ff9a00 25%,
			#ff8f03 27.5%,
			#ff8414 30%,
			#ff5634 40%,
			#ff164a 50%,
			#fd004f 52.5%,
			#e9005d 60%,
			#c6006d 70%,
			#9a0079 80%,
			#640080 90%,
			#420081 95%,
			#000080 100%
		);
	}

	.banner div {
		color: white;
	}

	.main-content {
		display: flex;
		flex-direction: row;
		height: 100vh;
		width: 100vw;
	}

	.color-palette {
		flex: 1;
		height: 70px;
	}

	.color-palette input {
		width: 100%;
		height: 100%;
		border: none;
		background: none;
		color: white;
		font-size: 2rem;
		text-align: center;
	}

	.color-palette .swatch {
		width: 100%;
		height: 100%;
	}
</style>
