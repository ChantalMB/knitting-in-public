<script>
import Header from "$lib/Header.svelte";

import AudioPlayer from "$lib/modules/AudioPlayer.svelte";

let allsounds = ['/soundscapes/spinning.mp3', '/soundscapes/Great Wheel Spinning-97FaL9xigJU.mp3']

</script>

<Header />

<!-- svelte-ignore a11y-mouse-events-have-key-events -->
{#each allsounds as src, i}
	<div style="top:{(100*Math.random()) + "%"}; left: {(100*Math.random()) + "%"}">
    	<AudioPlayer {src} />
	</div>
{/each}

<style>
    html, body {
        position: relative;
        width: 100%;
        height: 100%;
    }

    body {
        color: #333;
        margin: 0;
        padding: 8px;
        box-sizing: border-box;
        font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
    }
    .parallax-container {
		position: fixed;
		width: 2400px;
		height: 712px;
		left: 50%;
		transform: translate(-50%,0);
	}

	.parallax-container img {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		will-change: transform;
	}

	.parallax-container img:last-child::after {
		content: '';
		position: absolute;
		width: 100%;
		height: 100%;
		background: rgb(45,10,13);
	}

	.text {
		position: relative;
		width: 100%;
		height: 300vh;
		color: rgb(220,113,43);
		text-align: center;
		padding: 4em 0.5em 0.5em 0.5em;
		box-sizing: border-box;
	}

	a, span {
		color: rgb(220,113,43);
		display: block;
		font-size: 1em;
		text-transform: uppercase;
		will-change: transform, opacity;
	}

	#foreground0 {
		position: absolute;
		top: 711px;
		left: 0;
		width: 100%;
		height: calc(100% - 712px);
		background-color: #C4355E;
		color: white;
		padding: 50vh 0 0 0;
	}

	#foreground1 {
		position: absolute;
		top: 1422px;
		left: 0;
		width: 100%;
		height: calc(100% - 1423px);
		background-color: rgb(32,0,1);
		color: white;
		padding: 50vh 0 0 0;
	}

	#foreground2 {
		position: absolute;
		top: 2133px;
		left: 0;
		width: 100%;
		height: calc(100% - 2134px);
		background-color: rgb(32,0,1);
		color: white;
		padding: 50vh 0 0 0;
	}

	:global(body) {
		margin: 0;
		padding: 0;
		background-color: rgb(253, 174, 51);
	}
</style>