<script>
    import { fly, blur } from "svelte/transition";
    import Header from "$lib/Header.svelte";
	import { goto } from '$app/navigation';

</script>

<div id="page">
    <div id="header" in:blur|local={{ duration: 700 }}>Acknowledgements & References</div>

    <div class="info-card">
        fklwfk
    </div>
</div>

<div on:click={() => goto(`/five`)} id="click-left" >
	<div class="arrow-left"></div>
</div>

<style>

    #header {
        position: static;
        z-index: 1000;
        font-family: 'Kollektif';
        font-weight: bold;
        font-size: 57pt;
        bottom: 30%;
        text-align: center;
        color: #D51F5D;
    }

    .info-card {
        position: relative;
        z-index: -1;
        margin: auto;
        overflow: visible;
        width: 87vw;
        height: auto;
        background: lightpink;
        box-shadow: 5px 10px hotpink;
        border-radius: 5px;

        font-family: 'Archivo Narrow';
        color: #24305e;
    }

</style>