<script>
    import { fly, blur } from "svelte/transition";
    import Header from "$lib/Header.svelte";
	import { goto } from '$app/navigation';

</script>

<div class="page">
    <div id="title" in:blur|local={{ duration: 700 }}>Knitting as Feminine</div>

    <div class="info-card">
        <div id="text-content">

            <img id="lit-glove" src="/images/lit-garment.png"/>

            <p>Although the early history of knitting is ambiguous, we do know that it was not always inherently gendered. The first knitted garment uncovered was from Northern Africa, and produce around the 12th century AD; because this garment consisted of complex stitching and colour work, it is likely that knitting existed long before this item’s creation. The art of knitting was thought to have been brought to Europe through Spain following the Islamic Conquests or through Spain’s religious crusades, yet knitting did not gain widespread popularity until the early modern period. European knits prior to this period were found only in the tombs of Spanish nobles or religious officials, and consisted of small accessories or liturgical garments, suggesting that knitting during this time was potentially something imported and exclusive to the wealthy.</p>
            
            <p>The rise in demand for knitted goods in the late 15th century is often attributed to the rising male fashion of the time that consisted of knee-length breeches designed to show off the lower leg, which were covered by tightly fitted stockings. Stockings were originally made from woven fabric fitted to the individual wearer’s leg, but this woven material could not compete with the close fit and stretch that was characteristic of knitted fabric. This high demand for stockings among other knit goods led to the formation of knitting guilds, which were the first sites of knitting becoming a gendered activity.</p>
            
            <img id="breeches" src="/images/breeches.jpeg"/>

            <p>Despite there being less strictly defined gender roles in the early modern period compared to the period which followed it, there were still observed differences between the work that men and women did. Aside from duties of child-bearing and motherhood, according to a survey on the work patterns of women in England, Germany, and Sweden in early modern Europe by Whittle and Hailwood, it is suggested that the labour women performed was considered to be “low-status, low-paid and low-skilled”. When hand knitting became professionalized in the 15th century, it was considered a trade requiring a high level of skill which demanded a significant amount of available time for travel to learn and master; considering a woman’s expected responsibility to form and care for family, she would not have time to embark on the apprenticeships required to become “highly skilled” and join a knitting guild. This assumption led to knitting guilds often not allowing women to become members at all, and even if there was no explicit rule banning female apprentices or even no knitting guild at all in a given region, women still tended to perform the “simpler” labours of preparation in textile production, such as shearing the sheep and carding their wool.</p>
            
            <img id="stocking" src="/images/stocking-frame.jpg"/>

            <p>It was not until the advent of the stocking frame, the original knitting machine, in the late 16th century that women returned to knitting as a way to earn a wage. The stocking frame was initially met with strong resistance in the country of its invention, England, as there were numerous, large guilds of hand knitters and these men would lose a substantial portion of their their livelihood should machine knitting be permitted. Still, the use of the stocking frame was popularized in the 17th century after being exported then reintroduced to England from France, and soon factories opened to mass produce stockings using them. At this point in time, the making of stockings was not regulated by apprenticeships, thus women began to be employed in factories to aide in their production.</p>
            
            <p>It is this mechanization of knitting which serves as the turning point for the identity of a knitter becoming a feminine one. As industrialization progressed so did class division; bourgeoisie society blossomed as wealth for businessmen and tradesmen grew, and with this, women were pushed further into the sphere of domesticity, expected to not work should they be sufficiently supported by their husband’s wage. With this shift during the 18th and 19th century, leisure time for women grew and domesticity became the work of women who could afford it, so this time was inhabited by the creation of elaborate pieces of hand knitting, for in this industrious era only those who did not have to work had the time to learn such advanced skills. Although these same skills were once viewed as exclusive and highly profitable for the men working within guilds, with machine knitting occupying the means of production, hand knitting lost status within in the wider socioeconomic framework and was relegated to simply being a feminine quality respectable women were expected to possess. This framing of knitting is what situated it as the domestic craft it is recognized as today, and what conflated the image of a knitter with that of a woman.</p>

            <img id="fancy-lady" src="/images/18th-c-knitting.jpeg"/>
            
            <p>This feminine association with knitting was further solidified throughout the 19th and 20th century, most prominently via collective efforts such as the suffrage movement and wartime supports. Women who pursued the right to vote were often depicted as being undesirable and unfeminine since they sought a right that had historically only been offered to men in Western society. While some women did reject traditionally feminine activities such as knitting during the suffrage movement to protest existing societal structures, many more used this femininity to their advantage and in doing so outlined what it meant to be a “true” woman. 
                <img id="suffrage" src="/images/suffrage.jpeg"/>
                Suffragists periodicals frequently discussed women’s suffrage in the intertwined contexts of “true womanhood” as outlined by Barbara Welter— virtue, piety, purity, submissiveness and domesticity— expressed through representative craft. Among discussions of housewifery, marriage, and morals were discussions about handicrafts such as knitting. In adapting the separate spheres discourse and ideals of womanhood by painting themselves as the epitome of domesticity, and then performing this through the act of crafting what was published within these periodicals, suffragists were able to argue that these virtues and skills that they possessed could be carried from their private sphere into the public in order to “clean up” the immorality and corruption they felt was present. The role of knitting was present in a similar manner during war time in the 20th century. Women primarily occupied the homefronts as men left for war, and as a result many chose to take up laborious work both to support the war efforts and fill in the gaps which men had left behind. In both World War I and World War II there were campaigns to support the war effort through knitting goods that would be given to soldiers overseas, so although many women entered the masculinized world of work to support the war, they were also able to participate in these knitting campaigns which allowed them to reassert their femininity by offering a productive outlet to express both their morality and domesticity which their womanhood was tied to.</p> 


            <p>It is this history of constructed womanhood that is present within the identity of a knitter today. When the public audience views my performance of knitting, they also view me as performing this domestic femininity so entrenched within the remembered history of this craft. A knitter is assumed to be feminine, and in being feminine the associated traits of womanhood are something that a knitter is also expected to possess by onlookers, unless their appearance explicitly subverts this expectation. My interaction with this person on the train speaks to an expectation of domesticity, where in bringing my knitting into a public space I am bringing something perceived as private or leisurely— done within the confines of the home— into the realm of work, therefore it may be assumed that this is something I intend to sell. There's also the expectation that I am passive, deriving from the notion of submissiveness as feminine, that feeds into the entitlement that women may be touched regardless of consent, and by extension so may her craft.</p>

        </div>
    </div>
</div>

<div class="navigation">
<div on:click={() => goto(`/two`)} id="click-left" >
	<div class="arrow-left"></div>
</div>

<div on:click={() => goto(`/four`)} id="click-right" >
	<div class="arrow-right"></div>
</div>
</div>

<style>
    :global(body) {
        overflow: auto;
    }

    #click-left, #click-right {
        position: fixed;
        bottom: 0;
    }

	#title {
        position: static;
        z-index: 1000;
        font-family: 'Kollektif';
        font-weight: bold;
        font-size: 57pt;
        bottom: 30%;
        text-align: center;
        color: #24305e;
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

    #text-content {
        padding: 35px;
    }

    p {
        text-align: justify;
    }

    #lit-glove {
        float: left;
        width: auto;
        height: 550px;
        margin-left: -150px;
        margin-top: -150px;
        padding: 0px 5px 0px 5px;
    }

    #breeches {
        float: right;
        width: auto;
        height: 500px;
        margin-right: -100px;
        padding: 0px 15px 0px 15px;
    }

    #stocking {
        float: left;
        width: auto;
        height: 400px;
        margin-left: -85px;
        padding: 0px 15px 0px 15px;
    }

    #fancy-lady {
        float: right;
        width: auto;
        height: 500px;
        margin-right: -90px;
        padding: 0px 15px 0px 15px;
    }

    #suffrage {
        float: left;
        width: auto;
        height: 500px;
        margin-left: -90px;
        padding: 15px 15px 0px 15px;
    }

    
</style>