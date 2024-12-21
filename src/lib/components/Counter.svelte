<script lang="ts">
	let count = $state(0);

	function increment() {
		count += 1;
	}
</script>

<span>Counter</span>
<div class="flex w-fit gap-2 border border-gray-300 p-2">
	<input
		type="text"
		disabled
		bind:value={count}
		class="w-32 border border-gray-300 px-4 focus:outline-none"
	/>
	<button onclick={increment} class="w-fit border border-gray-300 px-2">Count</button>
</div>
