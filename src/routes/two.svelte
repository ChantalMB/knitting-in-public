<script>
    import { fly, fade } from "svelte/transition";
    import Header from "$lib/Header.svelte";
	import { goto } from '$app/navigation';

    let show = false;
</script>

<div class="page">
    
    <div id="shawl" in:fly|local={{ y: -200, duration: 2000 }}>
        <img src="../static/images/full_shawl.png"/>
    </div>

    <div id="dialogue-1">
        <div id="text-1" in:fade|local={{ y: -200, delay: 3000, duration: 1000 }}>
            "oh, you're knitting?"
        </div>
        <div id="text-2" in:fade|local={{ y: -200, delay: 5000, duration: 1000 }}>
            [laugh]
            "yes! it gives me som-"
        </div>
    </div>

    <div id="grab" in:fly|local={{ x: 200, delay: 6000, duration: 2000 }}>
        <img src="../static/images/grab.png"/>
    </div>

    <div id="dialogue-2">
        <div id="text-3" in:fade|local={{ x: 200, delay: 8000, duration: 1000 }}>
            [grabs my knitting]
        </div>
        <div id="text-4" in:fade|local={{ x: 200, delay: 8000, duration: 1000 }}>
            "ah I see,
        </div>

        <div id="text-5" on:click={() => goto(`/three`)} in:fade|local={{ x: 200, delay: 10000, duration: 1000 }}>
            you're making this to sell."
        </div>
            
    </div>

</div>

<div class="navigation">
    <div on:click={() => goto(`/one`)} id="click-left" >
        <div class="arrow-left"></div>
    </div>
</div>


<style>
    :global(body) {
        overflow: hidden;
        font-family: 'Courier New', Courier, monospace;
        font-weight: bold;
    }

    div {
        color: #faeddd;
    }

    #dialogue-1 {
        margin: 10px;
        position: absolute;
        top: 7%;
        left: 30%;
        float: right;
    }

    #dialogue-2 {
        float: left;
    }

    #text-1, #text-2 {
        padding: 30px;
        font-size: 37px;
    }

    #text-1 {
        text-shadow: 2px 2px 2px #24305e;
    }

    #text-2 {
        color: rgb(221, 150, 43);
        margin-top: 2.5%;
        text-shadow: 2px 2px 2px #cb4b16;

    }


    #text-3 {
        padding: 5px;
        font-size: 25px;
        font-weight: normal;
        position: absolute;
        left: 65.7%;
        bottom: 23.9%;
    }

    #text-4 {
        padding: 15px;
        font-size: 37px;
        position: absolute;
        bottom: 21.5%;
        left: 21%;
        text-shadow: 2px 2px 2px #24305e;

    }

    #text-5 {
        padding: 20px;
        font-size: 50px;
        position: absolute;
        bottom: 9%;
        left: 13%;
        text-shadow: 2px 2px 2px #24305e;

        -webkit-text-stroke: 0.15px #24305e;
        cursor: pointer;
        z-index: 1;
        animation: pulse 3s infinite alternate;
    }
	

    @keyframes pulse {
        to {
            text-shadow: 0 0 10px white;
        }
    }

    img {  
        width: 100%;
        height: auto;
    }  

    #shawl {
        position: relative;
        width: 290px;
        height: 300px;
        left: 5%;
    }

    #grab {
        position: relative;
        width: 590px;
        height: 390px;
        left: 57.5%;
        top: 5%;
    } 

</style>