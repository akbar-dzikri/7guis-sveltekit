<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<main class="flex flex-wrap items-center justify-center gap-4 p-4">
	{@render children()}
</main>
