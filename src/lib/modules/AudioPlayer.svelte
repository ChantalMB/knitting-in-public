<script context="module">
	import { tweened } from 'svelte/motion';
  const players = new Set()

  export function stopAll() {
    players.forEach(p => p.pause())
  }
</script>

<script>
  import { onMount } from 'svelte';

  export let src;
  export let place;

  let player;

  onMount(() => {
    // Like players.push(player)
    players.add(player)
  })
	
	let volume = tweened(1, { duration: 3000 })
	$: if (player) { player.volume = $volume }

	function handleMouseOver(e) {
			$volume = 1;
			player.play();
	}

	function handleMouseOut(e) {
			$volume = 0;
			// thissound.currentTime = 0;
	}
</script>

<div>
	<!-- svelte-ignore a11y-mouse-events-have-key-events -->
	<p on:mouseover={handleMouseOver} 
    	on:mouseout={handleMouseOut}>
        {place[3]}
  	</p>
	<audio
		bind:this={player}
		{src}
		>
		<track kind="captions" />
	</audio>
</div>

<style>
	/* .audio {
		display: inline-block;
	} */
</style>