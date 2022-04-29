<script>
    import { slide, fade } from "svelte/transition";
    import Header from "$lib/Header.svelte";
	import { goto } from '$app/navigation';
    import AudioPlayer from "$lib/modules/AudioPlayer.svelte";

    let showCard;

    let sounds = {
                    '/soundscapes/spinning.mp3': [1, 67.5, 11, "\"P.S. Doll at the Ferry must be taught to Knit, and made to do a sufficient days work of it—otherwise (if suffered to be idle) many more will walk in her steps.\""],
                    '/soundscapes/edwardian.m4a': [-24.5, 25, 13, "\"The idea of modesty and virtue in a Louisiana colored girl might well be ridiculed; as a general thing she has neither.\""],
                    '/soundscapes/suffrage.m4a': [-19, 3, 11, "\"It is not fair that they should vote, nor is it fair that a plantation negro who can neither read nor write should be entrusted with the ballot.\""],
                    '/soundscapes/london-streets.m4a': [70, 20, 12, "\"Intended only for persons who dress well and who appreciate first class illustrations and literature.\""],
                    '/soundscapes/sm.m4a': [39, 61, 13, "\"And it just keeps getting more and more expensive and elitist, until only other white women can keep up.\""]
                }
    let show = false;
    let card = false;

    function toggleShow() {
        console.log("hi")
        show = !show;
    }

    function toggleCard() {
        console.log("hi");
		card = !card;
    }

    function displayText(src) {
        if (src === '/soundscapes/spinning.mp3') {
            showCard = "spinning";
            toggleCard()
        } else if (src === '/soundscapes/edwardian.m4a') {
            showCard = "edwardian";
            toggleCard()
        } else if (src === '/soundscapes/suffrage.m4a') {
            showCard = "suffrage";
            toggleCard()
        } else if (src === '/soundscapes/london-streets.m4a') {
            showCard = "streets";
            toggleCard()
        } else if (src === '/soundscapes/sm.m4a') {
            showCard = "sm";
            toggleCard()

        }
    }

</script>

<div class="page">
    <div in:fade|local={{ y: -200, delay: 4000, duration: 1000 }}>
    {#each Object.entries(sounds) as [src, place]}
        <div on:click={()=>displayText(src)} class="audio" style="position:relative; left:{place[0]}vw; top:{place[1]}vh; font-size:{place[2]}pt; max-width:27.5%;">
            <AudioPlayer {src} {place} />
        </div>
    {/each}
    </div>

    <div class="mo">
        <div id="mo-context">
            <img class="mo-img" in:fade|local={{ duration: 1000 }} id="mo-pic" src="/images/mo-pic.svg"/>
            <img class="mo-img" in:fade|local={{ y: -200, delay: 2000, duration: 1000 }} id="mo-if" src="/images/mo-if-pic.svg"/> 
            <img class="mo-img" in:fade|local={{ y: -200, delay: 3000, duration: 1000 }} id="mo-why" src="/images/mo-why-pic.svg"/>
            
            <div id="infoOverlay" on:mouseenter={toggleShow}>
                {#if show}
                    <p id='mo-kg-info' in:fade|local={{ y: -200, delay: 1000, duration: 1000 }}>Michelle Obama graced the cover of Vogue Knitting magazine’s Winter 2021 issue, the featured story being about her experience becoming a knitter over the course of the COVID-19 pandemic. While many were excited by this representation, the cover was also met with petty criticism from prominent members of the knitting community, revealing the underlying standard of whiteness that has been set for those identified as a knitter. With subconscious narratives shaped by centuries of exclusion, when the knitter becomes the audience these narratives that have been ignored resurface.</p>
                {/if}
            </div>
                {#if show}
                    <img class="mo-img" transition:fade|local={{ duration: 1000 }} id="overlay" src="/images/mo-overlay.svg"/>
                    <div id="mo-context" on:click={toggleShow}></div>
                {/if}
            </div>
    </div>

    {#if card}
        <div
            class="card"
            id="cardOverlay"
            transition:fade="{{ duration: 500 }}"
            on:click={toggleCard}>

            <div class="info-card">
                {#if showCard === "spinning"}
                <i><h3><a href="https://founders.archives.gov/documents/Washington/05-11-02-0182">“From George Washington to Anthony Whitting”, 4 November 1792</a></h3></i>

                <p>In colonial America, the &ldquo;low-status, low-paid and low-skilled&rdquo; work that women performed in Europe carried over the work expected to be performed by slaves, yet slaves typically went unpaid. Life in the colonies was much less industrialized than life in Europe during the 17th and 18th centuries. Machine knitting was not established until the 19th century, so the production of textiles was done by hand and mostly on home soil, as importing items from Europe was both an expensive and lengthy process. Thus, out of necessity, all women living in colonial America were capable of knitting at least essential garments, such as stockings. Still, not all knitting was seen as equal&mdash; a concept which was revealed exceptionally so on the American plantations. Resources were scarce but plantation owners and their slaves still needed to be clothed, so slaves were employed to knit stockings by hand among performing other modes of textile production. The most complete documentation of accounts related to slave labour and knitting are found in the Washington Papers, a collection of George Washington&apos;s personal and private documents from 1748 to 1799.</p>
                <p>Washington fretted an exceptional amount about the production of stockings, which he felt there was never enough of, and he made this unhappiness known when discussing the productivity of his plantation&mdash;referred to as Mount Vernon&mdash;in his letters to friends. These complaints are telling about watch was considered &ldquo;good&rdquo; and &ldquo;bad&rdquo; knitting, and who produced it. From documents detailing what Washington purchased, we know that he purchased knitted goods from others off the plantation, likely from white women who sold their garments in the markets, and further, he also imported finer hosiery from London merchants as many other wealthy Americans did. His consumption of knit goods created a dichotomy that place the knitting done outside of the plantation by white individuals as being of greater value than the knitting performed by his own slaves. Washington also does not complain about the stockings he had purchased, yet the knitting performed by his slaves often faced intense scrutiny for both its quality and quantity. In discussing how two of his designated textile workers&mdash; Doll, as referenced in the quote for this section, and a man referred to as &ldquo;lame Peter&rdquo;&mdash; only produced 60 pairs of stockings, Washington threatens to send them to another plantation to perform &ldquo;common labour&rdquo; should their level of production not improve. In another letter in discussing the standard of their work, he states:</p>
                <blockquote>&ldquo;The same attention ought to be given to Peter (and I suppose to Sarah likewise) or the Stockings will be knit too small for those for whom they are intended; such being the idleness, and deceit of these people.&rdquo;</blockquote>
                <p>The knitting of his slaves was also said to be poorly fit, and this is attributed to an inherent malice and laziness associated with black individuals rather than the fact that many of these slaves had only learn to knit a handful of years prior, when they arrived in America.</p>
                <p>As white women move towards knitting as leisure, and hence towards the modern perceived identity of a knitter, black woman were trapped in systems of slavery and barely acknowledged as women at all. Black women were labourers rather than knitters as white women were, even when the motions being performed were the same.</p>
                {:else if showCard === "edwardian"}
                <i><h3><a href="https://books.google.ca/books?id=SSY4AQAAMAAJ&pg=RA1-PA120&lpg=RA1-PA120&dq=%22The+idea+of+modesty+and+virtue+in+a+Louisiana+colored+girl+might+well+be+ridiculed;+as+a+general+thing+she+has+neither%22&source=bl&ots=25GInPb64u&sig=ACfU3U2lJ23kOddg8r_TikGctEzxtcliVg&hl=en&sa=X&ved=2ahUKEwjsncGd2rP3AhWKW80KHVnsDycQ6AF6BAgCEAM#v=onepage&q=%22The%20idea%20of%20modesty%20and%20virtue%20in%20a%20Louisiana%20colored%20girl%20might%20well%20be%20ridiculed%3B%20as%20a%20general%20thing%20she%20has%20neither%22&f=false">The Unionist's Daughter: A Tale of the Rebellion in Tennessee, 1861</a></h3></i>
                <p>In the formation of true womanhood and femininity as discussed previously, black women were barred from entry. They may be pious, but they could not be pure nor virtuous by merit of their race, and in largely being members of the working class post-abolition, they were excluded from the middle class ideal of domesticity. In North America, black women certainly knit as an economical means to cloth themselves and their families, but this was done out of necessity rather than leisure, therefore it was not performing domesticity in the &ldquo;correct&rdquo; manner.</p>
                <img id="sorjourner" src="/images/sorjourner.jpg"/>
                <p>Despite this ostracism, knitting as a symbol of femininity was still used by black women to protest their exclusion from the cult of womanhood. In a number of portraits, activist Sojourner Truth chose to pose with her knitting in hand; this choice was likely to assert her femininity, and in turn clearly state that she was as much of a woman as her white counterparts. Although these efforts ultimately did not change who a knitter was thought to be in the eyes of the public, the presence of knitting was used as a means to identify oneself as a knitter and the associated identities which accompanied this.&nbsp;</p>
                
                {:else if showCard === "suffrage"}
                <i><h3><a href="https://www.britishnewspaperarchive.co.uk/viewer/bl/0002947/18940521/010/0003">“White and Black in America: An Interview with Miss Willard”, 21 May 1894</a></h3></i>
                <p>In fighting for both abolition and suffrage, white women&rsquo;s protest was frequently performed within the confines of femininity, holding crafting &ldquo;bees&rdquo; in which they would collectively knit, spin, or sew while discussing their cause. The women who took part in these events were often motivated to protest because of the way in which these political causes affected their idea of womanhood. In arguing for abolition, many believed that as good Christian woman, they could not allow for the brutalities of slavery to continue.&nbsp;</p>
                
                <p>In spite of holding these beliefs, freed black women were still not permitted to participate in these bees alongside white women. They were excluded just as poor women were by classism, but further, white women still perceived black women as being members of a lesser race. They disagreed with the cruelty of slavery yet still did not want to uplift black women as their sociopolitical equals. As mentioned in the discussion of knitters as feminine, part of the moral cleansing which white suffragists desired to perform using the vote was to &ldquo;dilute&rdquo; the vote of male African Americans and immigrants who had been enfranchised prior, as this was seen as threatening the power of the dominant class. Once again, black women were deliberately excluded from performing these publicised acts of femininity and in turn were once again removed from the identities that compose what it is to be a knitter.</p>
                
                {:else if showCard === "streets"}
                <i><h3><a href="https://books.google.ca/books?id=15MQ0Pb1m8QC&pg=PT93&lpg=PT93&dq=%22Intended+only+for+persons+who+dress+well+and+who+appreciate+first+class+illustrations+and+literature.%22&source=bl&ots=ceLNBTmJtb&sig=ACfU3U0LCydvW0OsTe9IGSRxKmHi2GebcQ&hl=en&sa=X&ved=2ahUKEwi79KLz1LP3AhWoAZ0JHf0qDKQQ6AF6BAgCEAM#v=onepage&q=%22Intended%20only%20for%20persons%20who%20dress%20well%20and%20who%20appreciate%20first%20class%20illustrations%20and%20literature.%22&f=false">Vogue Knitting Advertisement in Scribner's Magazine, July 1897</a></h3></i>

                <img id="vk" src="/images/vk.png"/>

                <p>With the 19th century rise in middle class wealth coupled with knitting now occupying much of the leisure time of this dominant class, the demand for supplies grew. Further, with shopping now being perceived as an appropriate past time for these white, economically and socially privileged women, advertising began to target them by appealing to how they spent their time of leisure. It is at this point that knitting became firmly entrenched in whiteness. Media depicting knitting with illustrations of women, men and children modelling or handling the yarn, pattern, or notions being advertised were universally white, reflecting the ideals of femininity that the women they were marketing towards possessed, or at least, should possess. Vogue Knitting exemplified this; in launching the magazine during the late 19th century, their covers featured eye-catching fully coloured illustrations, yet any image depicting a body featured white skin. These covers sold the concept that a knitter was white, excluding black women from the narrative entirely.</p>
                
                <p>As a concluding note, the first time a black woman ever appeared on the cover of Vogue Knitting was in 1993. Since then, only 7 other covers have featured black women.</p>
                
                
                {:else if showCard === "sm"}
                <i><h3><a href="https://www.vox.com/the-goods/2019/2/25/18234950/knitting-racism-instagram-stories">“The Knitting Community is Reckoning with Racism”, 25 February 2019</a></h3></i>

                <p>With the rise of social media there is increasing diversity within the knitting community in all categories of difference&mdash;age, race, and class&mdash;yet middle class white women still hold not only the dominant, but most powerful voices.</p>
                
                <p>The cost towards influence in the knitting community requires not only the time to become talented in the craft, but also money to spend on luxurious yarn that is valued much higher than what is found in large-chain craft stores. This underlying classism impairs marginalized voices to from being heard, as they still suffer from the histories of racism which oppressed them. &nbsp;</p>
                
                <p>When black women do gain affluence in the knitting community, they are only accepted in this predominantly white setting if they stay silent. If they talk about their experiences of race within the community, they are often met with backlash and told that a knitting account is not the form for such discussions; they should not make knitting political. Even the very image of a black women knitting can result in harsher scrutiny of their craft and accusations of being too &ldquo;political&rdquo;; in an interview of black knitters who participate in these crafting communities through Ravelry, Instagram, and Etsy, it was common for these women to recruit lighter skinned friends to model their finished objects in photographs, or refrain from using images of their own face or hands online to increase the reach of their profiles and avoid racist commentary. In the thought of bell hooks, these responses indicate blindness to ethnic privilege and a sense that white crafters &ldquo;own&rdquo; the movement to which people of color might enter.</p>
                
                
                {/if}
            </div>

        </div>
    {/if}
</div>

<div class="navigation">
    <div on:click={() => goto(`/three`)} id="click-left" >
        <div class="arrow-left"></div>
    </div>

    <div on:click={() => goto(`/five`)} id="click-right" >
        <div class="arrow-right"></div>
    </div>
</div>

<style>
    :global(body) {
        overflow: hidden;
    }

    .audio {
        position: absolute;
        display: inline-block;
        z-index: 3;
        font-family: 'Playfair Display';
        font-weight: 500;
        font-size: 12.3pt;
        text-align: center;
        color: #D51F5D;
    }

    #mo-context {
        position: absolute;
        width:150vw;
        height:150vh;
        top: 55%;
        left: 50%;
        transform: translate(-50%, -50%);
        
    }
    
    .mo-img {  
        max-width: 100%;
        height: auto;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    } 

    #mo-pic, #mo-if, #mo-why, #overlay{
        position: absolute;
    }

    #infoOverlay {
        width:23%;
        height:auto;
        position: absolute;
        top: 49.3%;
        left: 49.35%;
        transform: translate(-50%, -50%);
        aspect-ratio: 1 / 1;
        z-index: 1;
    }

    #overlay {
        opacity: 90%;
    }

    #mo-kg-info {
        text-align: center;
        font-family: 'Archivo Narrow';
        margin-top: 11%;
        color: #24305e;
    }

    #cardOverlay {
        position: fixed;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: rgba(0, 0, 0, 0.5);
        z-index: 1000;
        cursor: pointer;
    }

    .info-card {
        position: relative;
        z-index: 1;
        margin-top: 55px;
        width: 87vw;
        height: auto;
        background: #8ad3bf;
        color: #24305e;
        box-shadow: 5px 10px #24305e;
        border-radius: 5px;

        top: 35%;
        left: 50%;
        transform: translate(-50%, -50%);

        font-family: 'Archivo Narrow';
        padding: 35px;
    }

    #sorjourner {
        float: left;
        width: auto;
        height: 450px;
        margin: 0px 15px 0px 15px;
    }

    #vk {
        float: right;
        width: auto;
        height: 450px;
        margin: 0px 15px 0px 15px;
    }
  

</style>