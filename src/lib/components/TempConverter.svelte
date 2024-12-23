<script lang="ts">
	let celcius: string = $state('');
	let fahrenheit: string = $state('');

	function onCelciusChange() {
		if (celcius === '' || /^[0-9]*$/.test(celcius)) {
			if (Number(celcius) === 0) {
				fahrenheit = '';
			} else {
				const f = Number(celcius) * (9 / 5) + 32;
				fahrenheit = f.toFixed(2);
			}
		} else {
			celcius = '';
		}
	}

	function onFahrenheitChange() {
		if (fahrenheit === '' || /^[0-9]*$/.test(fahrenheit)) {
			if (Number(fahrenheit) === 0) {
				celcius = '';
			} else {
				const c = (Number(fahrenheit) - 32) * (5 / 9);
				celcius = c.toFixed(2);
			}
		} else {
			fahrenheit = '';
		}
	}
</script>

<span>Temperature Converter</span>
<div class="flex w-fit gap-2 border border-gray-300 p-2">
	<input
		type="text"
		bind:value={celcius}
		oninput={onCelciusChange}
		class="w-32 border border-gray-300 px-4 focus:outline-none"
	/>
	<input
		type="text"
		bind:value={fahrenheit}
		oninput={onFahrenheitChange}
		class="w-32 border border-gray-300 px-4 focus:outline-none"
	/>
</div>
