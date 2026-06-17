<script>
	import favicon from '$lib/assets/icons8-cupcake-32.png';

	import "$lib/styles.css";

	let { children } = $props();
</script>
<style>
	#background {
		position: absolute;
		top: 0;
		right: 0;
		left: 0;
		bottom: 0;
		z-index: 0;
		background-image: repeating-linear-gradient(30deg, purple, purple 25px, rgb(131, 56, 144) 25px, rgb(131, 56, 144) 50px)
	}
</style>

<svelte:head>
	<title>Olive Garden :P</title>
	<link rel="icon" href={favicon} />
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Epilogue:ital,wght@0,100..900;1,100..900&family=Gamja+Flower&family=Indie+Flower&family=Meow+Script&family=Nanum+Brush+Script&family=Oleo+Script:wght@400;700&family=Pacifico&family=Playwrite+CA:wght@100..400&display=swap" rel="preload" as="style">
	<link href="https://fonts.googleapis.com/css2?family=Epilogue:ital,wght@0,100..900;1,100..900&family=Gamja+Flower&family=Indie+Flower&family=Meow+Script&family=Nanum+Brush+Script&family=Oleo+Script:wght@400;700&family=Pacifico&family=Playwrite+CA:wght@100..400&display=swap" rel="stylesheet">
	<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200&icon_names=refresh" />
</svelte:head>

<div id="background"></div>
{@render children()}

