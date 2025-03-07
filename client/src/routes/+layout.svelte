<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<main class='bg-gray-950 text-white w-screen h-screen absolute top-0 left-0'>
    {@render children()}
</main>