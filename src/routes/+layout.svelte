<script>
	import favicon from '$lib/assets/favicon.svg';

	import "$lib/styles.css";

	let { children } = $props();
</script>

<svelte:head>
	<title>Olive Garden :P</title>
	<link rel="icon" href={favicon} />
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Epilogue:ital,wght@0,100..900;1,100..900&family=Gamja+Flower&family=Indie+Flower&family=Oleo+Script:wght@400;700&family=Playwrite+CA:wght@100..400&display=swap" rel="stylesheet">
</svelte:head>

{@render children()}
