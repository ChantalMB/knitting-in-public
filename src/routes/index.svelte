<script>
	import Header from "$lib/Header.svelte";
	import { tick } from "svelte";
	import { goto } from '$app/navigation';

	let y;
	let scrollToDiv;

	const layers = [0, 1, 2, 3];


    const preserveScroll = (url) => {
        goto(url, {
            noscroll: true,
        });
    };


	async function autoScroll() {
		await tick(); // Wait until DOM was updated
		let topCoord = scrollToDiv.getBoundingClientRect().top;

		window.scrollTo({ top: topCoord, behavior: 'smooth' }); // Scroll to the bottom of the container
	}

</script>

<svelte:window bind:scrollY={y}/>

<div class="parallax-container">
	{#each layers as layer}
		<img
			style="transform: translate(0,{-y * layer / (layers.length - 1)}px)"
			src="/parallax/parallax{layer}.png"
			alt="parallax layer {layer}"
		>
	{/each}
</div>

<div class="text">
	<div on:click={()=> autoScroll()} style="opacity: {1 - Math.max(0, y / 40)}" class="arrow"></div>


	<div bind:this="{scrollToDiv}" id="foreground0">
		<div class="conText">
			<div id="highlight">Performance plays a crucial role in the formation of culture.</div>
			<p>Likewise, culture plays a crucial role in the constitution of identity. When one adopts an identity they in turn immerse themselves into the culture surrounding this identity and ultimately learn from others within this culture how this identity should be, or is expected to be, enacted and performed. In collective memory, knitting is often conceptualized as a domestic activity done by women in the past, or women who at one point in time lived in this past. In recent history, knitting has had a resurgence in popularity amoung younger women who, in picking up a pair of needles, have begun to shift the culture of knitting from something exclusively associated with the elderly to something modern, and even trendy. With this cultural shift comes also a shift in identity; as an activity with a extensive past and active present, what shapes the identity of a "knitter" when these two points converge?</p>

			<p>The identity of "knitter" is both self-assigned by those who knit, yet also assigned by the audience who observe one engaged in the act of knitting. To be a knitter is therefore not only an identity shaped by those who perform the act of knitting, but also by those who have witnessed it in their own histories and have formed distinct definitions of who they believe a knitter is. The purpose of this site is to explore these intertwined historical narratives which have contributed to the construction of what it is to be a "knitter" through the perspectives of both knitters as the performer and knitters as an audience.</p>
			
			<div on:click={() => preserveScroll(`/one`)} id="next"> 
				<span>next</span>
				<div on:click={() => goto(`/two`)} id="click-demo">
					<div class="arrow-demo"></div>
				</div>
			</div>
		</div>

	</div>

</div>

<style>
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

	#foreground0 {
		font-family: 'Playfair Display';
		font-weight: 100;
		position: absolute;
		z-index: 1;
		top: 711px;
		left: 0;
		width: 100%;
		height: calc(100% - 712px);
		background-color: #D51F5D;
		color: #fdf6e3;
		padding: 13vh 0 0 0;
	}

	.arrow, .arrow:before {
		position: absolute;
		left: 50%; 
		z-index: 5;
	}

	.arrow {
		width: 40px;
		height: 40px;
		top: 93vh;
		margin: -20px 0 0 -20px;
		-webkit-transform: rotate(45deg);
		border-left: none;
		border-top: none;
		border-right: 2px #fdf6e3 solid;
		border-bottom: 2px #fdf6e3 solid; 
	}

	.arrow:before {
		content: '';
		width: 20px;
		height: 20px;
		top: 50%;
		margin: -10px 0 0 -10px;
		border-left: none;
		border-top: none;
		border-right: 1px #fdf6e3 solid;
		border-bottom: 1px #fdf6e3 solid;
		animation-duration: 2s;
		animation-iteration-count: infinite;
		animation-name: arrow; 
	}

	@keyframes arrow {
		0% {
			opacity: 1; }
		100% {
			opacity: 0;
			transform: translate(-10px, -10px); 
		} 
	}

	.conText {
		padding: 150px;
		max-width: 1500px;
		max-height: 150px;
		display: inline-block;

		
	}

	#highlight {
		color: rgb(255, 202, 116) ;
		text-shadow: 2px 2px 2px rgb(220,113,43);
		font-family: 'Kollektif';
		text-transform: uppercase;
		font-weight: 100;
		font-size: 35pt;
		margin: 7px;
	}

	#next {
		color: #8ad3bf;
		text-align: center;
		left: 50%;

	}

	#next span {
		color: #8ad3bf;
		display: inline-block;
		font-family: 'Kollektif';

	}

	#click-demo {
		margin-top: 5px;
		display: inline-block;
	}

	.arrow-demo {
		width: 13px;
		height: 13px;
		-webkit-transform: rotate(-50deg);
		border-left: none;
		border-top: none;
		border-right: 2px #8ad3bf solid;
		border-bottom: 2px #8ad3bf solid; 
	}
	

</style>
