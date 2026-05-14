<script>
    import { base } from "$app/paths";
    import { onMount } from "svelte"
    import { fly } from "svelte/transition";
    import { confetti } from '@neoconfetti/svelte';

    let screenX = $state(0);
    let screenY = $state(0);

    let fontCycle = ["Gamja Flower", "Indie Flower", "Oleo Script", "Nanum Brush Script", "Pacifico"];
    let fontScale = [1, 1, 0.8, 1.3, 0.7]
    let currFont = $state(fontCycle[2]);
    let fontIndex = $state(2);
    onMount(() => {
        setInterval(() => {
            fontIndex++; 
            if (fontIndex == fontCycle.length) {
                fontIndex = 0;
            }
            currFont = fontCycle[fontIndex]},
            1000)
    })

    let showImages = $state(false);
    onMount(() => {
        setTimeout(() => {showImages = true}, 500);
    })
</script>
<style>
    #title {
        position: absolute;
        z-index: 999;
        transform: translate(-50%, -50%,);
        top: 30px;
        width: 100%;
        user-select: none;

        .pushDown {
            transform: translateY(15px);
        }
    }
    #body {
        position: absolute;
        z-index: 997;
        transform: translate(-50%, -50%,);
        top: 150px;
        background-color: rgb(171, 80, 111);
        padding: 20px;
        border-radius: 20px;
        left: 15%;
        right: 15%;
        width: 70%;
        box-shadow: 0px 0px 20px 15px rgba(119, 119, 119, 0.498);
    }
    #confettiRight {
        position: absolute;
        top: 0;
        right: 50%;
        z-index: 997;
        overflow: crop;
    }

    #wave {
        position: fixed;
        bottom: -100vh;
        left: 0;
        right: 0;
        z-index: 999;
        transition: all 1s ease-in-out;
        user-select: none;
        -webkit-user-drag: none;
        -moz-user-select: none;
    }
    #penguin {
        position: fixed;
        bottom: -100vh;
        width: 100%;
        z-index: 998;
        transition: all 1.5s ease-in-out;
        transition-delay: 1500;
        user-select: none;
        -webkit-user-drag: none;
        -moz-user-select: none;
    }

    .up {
        bottom: -100px !important;
    }
</style>
<svelte:window bind:innerWidth={screenX} bind:innerHeight={screenY}></svelte:window>
<div use:confetti={{stageWidth: screenX*0.88, stageHeight: screenY*0.95}} id="confettiRight"></div>
<div id="title">
    <h1 class:pushDown={fontScale < 1}>Happy Birthday <span id="olive" style:font-family={currFont} style:font-size={40 * fontScale[fontIndex]}px style:color="pink">Olive</span>!</h1>
</div>
<div id="body">
    <h3>While I hate most things from New Jersey, you're actually pretty cool :P</h3>
    <h3>When you first sponsored The Zoo, the sites I had made for that were the first SvelteKit projects I had ever worked on; hopefully, this is better than those sites {">w<"}. Thanks for somehow trusting me enough to handle two YSWSs.</h3>
    <h4 style:font-family="Playwrite CA">Lynn</h4>
</div> 
<img src="{base}/images/olive.png" class:up={showImages} id="penguin" alt="Olive as a penguin"/>
<img src="{base}/images/wave.png" class:up={showImages} id="wave" alt="Wave graphic"/>