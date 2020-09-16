<script lang="ts">
	import { onMount, onDestroy } from 'svelte';
	let gameCanvas: Element
    import { game } from './game.js'
    let theGame = undefined;
	onMount(async () => {   
        theGame = game(gameCanvas)
        theGame.start()
	})
	onDestroy(async () => {   
        theGame.stop()
	})
</script>

<canvas id="game" bind:this={gameCanvas}/>