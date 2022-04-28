<script>
    import { fade, blur } from "svelte/transition";
    import Header from "$lib/Header.svelte";
	import { goto } from '$app/navigation';

    let show = false;
    let showCard;

    function toggleShow() {
		show = !show;
	}

    function toggleCard(src) {
        if (src === 'tank') {
            showCard = "tank";
            toggleShow()
        } else if (src === 'seeart') {
            showCard = "seeart";
            toggleShow()
        } else if (src === 'maman') {
            showCard = "maman";
            toggleShow()
        }
    }

</script>

<div class="page">

    <div in:fade|local={{ duration: 1000 }} id="header">Knitting in Public</div>
    <div in:fade|local={{ delay: 500, duration: 1000 }} id="exp">
        The presence of knitting in places or in forms unexpected creates a liminal space much like that of a play being performed in a park; the audience must pause in their journey from one place to the next to process what they are witnessing. This liminal space created by what has been termed &ldquo;knitffiti&rdquo; is what begins to alter the popular identity of &quot;knitter&quot; in the public eye; in the pause one acknowledges who is doing the knitting (if they are present) or considers who may have created the installation.
    </div>

    <div class="float-container">

    <a in:fade|local={{ delay: 1000, duration: 1000 }} id="tank">
        <img src="/images/tank.png"/> 
        <img on:click={()=>toggleCard('tank')} src="/images/tankshadow.png"/>    
    </a>

    <a in:fade|local={{ delay: 1500, duration: 1000 }} id="seeart">
        <img src="/images/seeart.png"/> 
        <img on:click={()=>toggleCard('seeart')} src="/images/seeartshadow.png"/>    
    </a>

    <a in:fade|local={{ delay: 2000, duration: 1000 }} id="maman">
        <img src="/images/maman.png"/> 
        <img on:click={()=>toggleCard('maman')} src="/images/mamanshadow.png"/>    
    </a>

    </div>


    {#if show}
        <div
            class="card"
            id="overlay"
            transition:fade="{{ duration: 500 }}"
            on:click={toggleShow}>

            <div class="info-card">
                {#if showCard === "tank"}
                <p>This form of truly public knitting is largely what has been promoted in third wave feminism; knitting is not only viewed as radical leisure but as a tool to advocate for causes deemed important. Knitting is assumed to be &ldquo;warm&rdquo;, feminine, and unthreatening, making it the perfect medium to voice concern. Modern women have commodified knitting much like their predecessors by taking already established monuments and reshaping their message through a layer of textiles. In this sense, knitters are inspired to reimagine the personal and private nature of this &ldquo;leisure&rdquo; in their construction of knitting as a communal, visible and performative practice.</p>
                {:else if showCard === "seeart"}
                <p>Yet, in spite of these positives, knitffiti still reinforces what was. The political actions of knitters are frequently dismissed as &ldquo;so nonconfrontational as to be completely ineffective . . . a safe form of activism (if it is even activism at all), both for those practicing it and those covering it in the media,&rdquo; stemming from a history of critical and political thought that is dismissive of both the feminine and the material.&nbsp;</p>
                <p>Further, the privilege of a knitter who is by default imagined to be white is further reinforced in their ability to perform knitffiti at all. Those partaking in public knitting and knitffiti are able to do so in broad daylight with little to no law enforcement being involved; something deeply ironic considering that graffiti, the art from which knitffiti derives its namesake, is heavily policed due to its origins with African American working-class men. Although occasionally subversive and warmly communal, the narratives which crafted the present default of who a knitter is must first be unraveled from within the knitting community before the larger public narrative of who is expected to knit can be redefined.</p>
                {:else if showCard === "maman"}
                <p>Knitffiti is not always explicitly political; in some knitting circles who partake, it is motivated by the notion of &ldquo;spreading joy&rdquo; and bringing colour to otherwise dark spaces within busy urban centres. These large-scale projects tend to be an expression of the both public and communal nature that has embodied modern knitting; rather than being done exclusively within the home among family or close friend, knitting has returned to being a group activity where those who partake can meet and work together in public spaces regardless of having known eachother prior. In doing this, the performance of a knitter has shifted; the knitter is now viewed as being part of a collective, whether formed intentionally or through silent demonstration as two strangers work on their projects sitting across from each other on the train ride home in the evening.</p>
                {/if}
            </div>

        </div>
    {/if}


</div>

<div class="navigation">
    <div on:click={() => goto(`/four`)} id="click-left" >
        <div class="arrow-left"></div>
    </div>
    <!-- <div on:click={() => goto(`/acknowledgements`)} id="click-right" >
        <div class="arrow-right"></div>
    </div> -->
</div>

<style>

    :global(body) {
        overflow: hidden;
        color: #24305e;
    }

    img {
        width: 100%;
        height: auto;
    }

    a img:last-child {
        display: none;  
    }
    a:hover img:last-child {
        display: inline-block;  
    }
    a:hover img:first-child {
        display: none;  
    }

    #overlay {
        position: fixed;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: rgba(0, 0, 0, 0.5);
        z-index: 2;
        cursor: pointer;
    }

    /* .float-container {
        display: flex;
    }

    .float-child {
        flex: 1;
    }  */
    
    #header {
        position: absolute;
        font-family: 'Kollektif';
        font-size: 30pt;
        font-weight: bold;
        text-align: left;
        top: 5%;
        left: 13%;
        transform: translate(-50%, -50%);
        padding: 15px 15px 0px 15px;

    }

    #exp {
        max-width: 500px;
        position: absolute;
        font-family: 'Playfair Display';
        font-size: 12pt;
        text-align: left;
        color: #24305e;
        top: 19.5%;
        left: 19%;
        transform: translate(-50%, -50%);
        padding: 15px;
        z-index: 5000;
    }

    .info-card {
        position: relative;
        z-index: 1;
        margin: 25px;
        overflow: visible;
        width: 87vw;
        height: auto;
        background: lightpink;
        box-shadow: 5px 10px hotpink;
        border-radius: 5px;

        top: 35%;
        left: 50%;
        transform: translate(-50%, -50%);

        font-family: 'Archivo Narrow';
        padding: 15px;
    }
  

    #tank {
        position: absolute;
        top: 57%;
        left: 1%;
        width:45vw;
        height:45vh;
        z-index: 2000;
    }

    #maman {
        position: absolute;
        top: 9%;
        left: 21%;
        width:71vw;
        height:71vh;
        z-index: 1000;
    }

    #seeart {
        position: absolute;
        top: 3%;
        left: 73%;
        width:25vw;
        height:105vh;
        z-index: 3000;
    }

    #click-left, #click-right {
        z-index: 7000;
    }
    

</style>