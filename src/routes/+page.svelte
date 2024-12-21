<script lang="ts">
	import type { Component } from 'svelte';

	const components: Record<string, { default: Component }> = import.meta.glob(
		'$lib/components/*.svelte',
		{ eager: true }
	);
</script>

{#each Object.values(components) as { default: Component }}
	<div class="flex flex-col gap-4">
		<Component />
	</div>
{/each}
