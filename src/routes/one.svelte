<script>
    import { fly, blur } from "svelte/transition";
    import Header from "$lib/Header.svelte";
	import { goto } from '$app/navigation';

    let show = false;
</script>
  
<div class="page">
    
    <div class="intro">
        <div id="h1" in:blur|local={{ duration: 700 }}>An Encounter on the Train</div>
        <div id="h2" in:blur|local={{ delay: 1000, duration: 700 }}>October 2019, in the morning</div>
    </div>

</div>

<div class="navigation">
    <div on:click={() => goto(`/`)} id="click-left" >
        <div class="arrow-left"></div>
    </div>

    <div on:click={() => goto(`/two`)} id="click-right" >
        <div class="arrow-right"></div>
    </div>
</div>

<style>
    .intro {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        color: #24305e;
    }

    #h1 {
        font-family: 'Kollektif';
        font-weight: bold;
        font-size: 35pt;
    }

    #h2 {
        font-family: 'Playfair Display';
        font-weight: 500;
        font-size: 21pt;
        text-align: center;
    }
    /* :global(body) {
        overflow: hidden;
    } */

</style>