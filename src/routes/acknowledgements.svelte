<script>
    import { fade, blur } from "svelte/transition";
    import Header from "$lib/Header.svelte";
	import { goto } from '$app/navigation';

    import LogoGithub from "carbon-icons-svelte/lib/LogoGithub.svelte";
    import UserAvatarFilled from "carbon-icons-svelte/lib/UserAvatarFilled.svelte";
    import HelpFilled from "carbon-icons-svelte/lib/HelpFilled.svelte";

    let show = false;

    function toggleShow() {
        console.log("hi")
        show = !show;
    }

</script>

<div id="page">
    <div id="header" in:fade|local={{ duration: 700 }}>Acknowledgements & References</div>
    <div id="icons">
        <span on:click={toggleShow}><HelpFilled size={24} /></span>
        <a href="https://github.com/ChantalMB/knitting-in-public"><LogoGithub size={24} /></a>
        <a href="https://chantalbrousseau.xyz/"><UserAvatarFilled size={24} /></a>
    </div>

    {#if show}
        <div class="bg-overlay" transition:fade="{{ duration: 500 }}" on:click={toggleShow}>
            <div id="context-card">
                This website was created as a final performance project for the course <a href="https://carleton.ca/history/graduate/graduate-seminars-2/hist-5707w-narrativity-and-performance-in-public-history/">HIST5707: Narrativity and Performance in Public History</a> as instructed by <a href="https://carleton.ca/history/people/david-dean/">Dr David Dean</a>. All illustrations and uncited photographs were produced by me, Chantal Brousseau, and the website itself was created using the <a href="https://kit.svelte.dev/">Sveltekit</a> web framework.
            </div>
        </div>
    {/if}

    <div class="info-card">
        <div id="info">
            <div class="subheader">Acknowledgements</div>
            <p>I would first like to thank all of my lovely Prof David Dean and classmates in HIST5707 who provided engaging conversations during our weekly seminars which ultimately inspired this project. Secondly, I would like to thank <a href="https://professordwj.com/">Dana Williams-Johnson</a> for generously sharing her NCA conference research with me, which served both as a reference, for her analysis of <i>Vogue Knitting</i> covers, and an excellent starting point for my conversation surrounding the narratives which formed the racial identity of a knitter.</p>

            <div class="subheader">Citations by Page</div>
            <br>
            <div class="subsubheader">Home Page</div>
            <p>Loxley, James. &quot;Performativity and Performance Theory.&quot; In <em>Performativity</em>, 139-166. Abingdon, Oxon: Taylor &amp; Francis Group, 2006.</p>

            <br>
            <hr>
            <div class="subsubheader">Three</div>
            <b>Images</b>
                <p><em>Bishop&#39;s Gloves</em>. c. fourth quarter 17th century, silk and metal, 5 x 12 in. (12.7 x 30.5 cm). The Metropolitan Museum of Art, New York. <a href="https://www.metmuseum.org/art/collection/search/156402">https://www.metmuseum.org/art/collection/search/156402.</a></p>
                <p>Moroni, Giovanni Battista. <em>Il Cavaliere in Rosa (The Man in Pink)</em>. 1560, oil on canvas, 85 x 48 3/8 in. (216 x 123 cm). Fondazione Museo di Palazzo Moroni, Bergamo. <a href="https://www.frick.org/exhibitions/moroni/35">https://www.frick.org/exhibitions/moroni/35</a>.</p>
                <p>Hinton, John. <em>The Art of Stocking-Frame-Work-Knitting</em>. 1750, print, 195 x 235mm. The British Museum, London. <a href="https://www.britishmuseum.org/collection/object/P_Y-4-429">https://www.britishmuseum.org/collection/object/P_Y-4-429</a>.</p>
                <p>Grundmann, Basilius. <em>Lady with Knitting Basket</em>. 1760, oil on wood, 18.9 x 15.36 in (48 x 39 cm). Greding, Germany. <a href="https://www.1stdibs.com/art/paintings/figurative-paintings/basilius-grundman-lady-knitting-basket-signed-grundman-dated-1760/id-a_9017062/">https://www.1stdibs.com/art/paintings/figurative-paintings/basilius-grundman-lady-knitting-basket-signed-grundman-dated-1760/id-a_9017062/</a>.</p>
                <p>Partridge, Bernard. &quot;A Temporary Entanglement,&quot; <em>Punch, or The London Charivari</em>, 18 April 1906. <a href="https://archive.org/details/punchvol130a131lemouoft/page/n314/mode/1up">https://archive.org/details/punchvol130a131lemouoft/page/n314/mode/1up</a>.</p>

            <b>Texts</b>
                <p>Groeneveld, Elizabeth. &quot;“Join the Knitting Revolution”: Third-Wave Feminist Magazines and the Politics of Domesticity.&quot; <em>Canadian Review of American Studies</em> 40, no. 2 (2010): 259-277. doi:10.1353/crv.2010.0006.</p>
                <p>Macdonald, Anne L. <em>No Idle Hands: The Social History of American Knitting</em>. New York: Ballantine Books, 1988.</p>
                <p>O&#39;Connell Edwards, Lesley. &quot;Working Hand Knitters in England from the Sixteenth to the Nineteenth Centuries,&quot; <em>Textile History</em> 41, no. 1 (2010): 70-85. doi:10.1179/174329510x12670196126647.</p>
                <p>Stalp, Marybeth C. &quot;Girls Just Want to Have Fun (Too): Complicating the Study of Femininity and Women&#39;s Leisure.&quot; <em>Sociology Compass</em> 9, no. 4 (2015): 261–271. doi: 10.1111/soc4.12260.</p>
                <p>Tirohl, Blu. “Now Wash Your Hands: Uncommissioned Art and Gender.” <em>Journal of Gender Studies</em> 25, no. 6 (2016): 693–704. doi:10.1080/09589236.2015.1136205.</p>
                <p>Thirsk, Joan. <em>The Rural Economy of England: Collected Essays</em>. London: Bloomsbury Publishing, 2003.</p>
                <p>Turnau, Irena. <em>History of Knitting Before Mass Production</em>. Translated by Agnieszka Szonert. Warsaw: Akcent, 1991.</p>
                <p>Turney, Joanne. <em>The Culture of Knitting</em>. Oxford: Berg Publishers, 2009.</p>
                <p>Welter, Barbara. “The Cult of True Womanhood: 1820-1860.” American Quarterly 18, no. 2 (1966): 151–74. <a href="https://doi.org/10.2307/2711179">https://doi.org/10.2307/2711179</a>.</p>
                <p>Whittle, Jane and Mark Hailwood. &quot;The Gender Division of Labour in Early Modern England.&quot; <em>Economic History Review</em>, 73, no. 1 (2020): 3-32. <a href="https://doi.org/10.1111/ehr.12821">https://doi.org/10.1111/ehr.12821</a>.</p>
            
            <br>
            <hr>
            <div class="subsubheader">Four</div>
            <b>Images</b>
                <p><em>Sojourner Truth</em>. 1864, albumen silver print, 8.1 x 5.7 cm (3 3/16 x 2 1/4&quot;). National Portrait Gallery, Washington. <a href="https://www.si.edu/object/sojourner-truth%3Anpg_NPG.78.207">https://www.si.edu/object/sojourner-truth%3Anpg_NPG.78.207</a>.</p>
                <p>Vogue Knitting, Winter 1993/1994. <a href="https://www.ravelry.com/patterns/sources/vogue-knitting-winter-94">https://www.ravelry.com/patterns/sources/vogue-knitting-winter-94</a>.</p>
            
            <b>Texts</b>
                <p>Close, Samantha. &quot;Knitting Activism, Knitting Gender, Knitting Race,&quot; <em>International Journal of Communication</em> 12, no. 23 (February 2018): 867–889. <a href="https://ijoc.org/index.php/ijoc/article/view/6122">https://ijoc.org/index.php/ijoc/article/view/6122.</a></p>
                <p>Dawkins, Nicole. &quot;Do-It-Yourself: The Precarious Work and Postfeminist Politics of Handmaking (in) Detroit.&quot; Utopian Studies 22, no. 2 (2011): 261-284. muse.jhu.edu/article/451895.</p>
                <p>Dirix, Emmanuelle. &quot;Stitched Up—Representations of Contemporary Vintage Style Mania and the Dark Side of the Popular Knitting Revival&quot;, <em>Textile: The Journal of Cloth and Culture</em> 12, no. 1 (2014): 86-99, <a href="https://doi.org/10.2752/175183514x13916051793550">https://doi.org/10.2752/175183514x13916051793550</a>.</p>
                <p>Hackney, Fiona. “‘Use Your Hands for Happiness’: Home Craft and Make-Do-and-Mend in British Women&#39;s Magazines in the 1920s and 1930s,” <em>Journal of Design History</em> 19, no. 1 (January 1, 2006): 23–38. doi:10.1093/jdh/epk003.</p>
                <p>Myzelev, Alla. &quot;Whip your hobby into shape: knitting, feminism and construction of gender.&quot; <em>Textile: The Journal of Cloth and Culture</em> 7, no. 2 (2009): 148-163. doi:10.2752/175183509x46oo65.</p>
                <p>Newington, Linda.&quot;“In the Loop”: Challenging and Disrupting the Stereotypes of Knitting,&quot; <em>Textile: The Journal of Cloth and Culture</em> 12, no. 1 (2014): 8-17. doi:10.2752/175183514x13916051793352.</p>
                <p>Orton-Johnson, Kate. “Knit, Purl and Upload: New Technologies, Digital Mediations and the Experience of Leisure.” <em>Leisure Studies</em> 33, no. 3 (May 4, 2014): 305–21. doi:10.1080/02614367.2012.723730.</p>
                <p>Saxena, Jaya. &quot;The Knitting Community is Reckoning with Racism,&quot; <em>Vox</em>, 25 Feb, 2019, 8:00am EST, The Goods, <a href="https://www.vox.com/the-goods/2019/2/25/18234950/knitting-racism-instagram-stories">https://www.vox.com/the-goods/2019/2/25/18234950/knitting-racism-instagram-stories</a>.</p>
                <p>Tirohl, Blu. “Now Wash Your Hands: Uncommissioned Art and Gender.” <em>Journal of Gender Studies</em> 25, no. 6 (2016): 693–704. doi:10.1080/09589236.2015.1136205.</p>
                <p>Vejlby, Anna Schram. &quot;Diligence and Emotion: Knitting in Danish Golden Age Portraiture,&quot; <em>Textile: Cloth and Culture</em> 14, no. 2 (2016): 188-207. doi:10.1080/14759756.2016.1165973.</p>
                <p>Williams-Johnson, Dana. &quot;How Knitting Became White: Analyzing 75 Years of Vogue Knitting Magazine Covers.&quot; Paper presented at the National Communications Association Conference, Washington State Convention Center, Seattle, 18 November 2021. <a href="https://ww4.aievolution.com/nca2101/index.cfm?do=ev.viewEv&amp;ev=16257">https://ww4.aievolution.com/nca2101/index.cfm?do=ev.viewEv&amp;ev=16257</a>.</p>
                <p>Wolfram Cox, Julie, and Stella Minahan. “Where Pop Meets Purl: Knitting, the Curation of Craft, and the Folk/Mass Culture Divide.” <em>Curator: The Museum Journal</em> 58, no. 3 (July 1, 2015): 235–49. doi:10.1111/cura.12111.</p>

            <br>
            <hr>
            <div class="subsubheader">Five</div>
                <p>Close, Samantha. &quot;Knitting Activism, Knitting Gender, Knitting Race,&quot; <em>International Journal of Communication</em> 12, no. 23 (February 2018): 867–889. <a href="https://ijoc.org/index.php/ijoc/article/view/6122">https://ijoc.org/index.php/ijoc/article/view/6122.</a></p>
                <p>Harrison, Katherine, and Cassandra A. Ogden. “‘Grandma Never Knit like This’: Reclaiming Older Women’s Knitting Practices from Discourses of New Craft in Britain.” <em>Leisure Studies</em> 38, no. 4 (July 4, 2019): 453–67. doi:10.1080/02614367.2019.1579852.</p>
                <p>Leslie A. Hahner &amp; Scott J. Varda &quot;Yarn Bombing and the Aesthetics of Exceptionalism,&quot; <em>Communication and Critical/Cultural Studies</em> 11, no. 4 (2014): 301-321. doi:10.1080/14791420.2014.959453.</p>
                <p>Loxley, James. &quot;Being Performative.&quot; In <em>Performativity</em>, 139-166. Abingdon, Oxon: Taylor &amp; Francis Group, 2006.</p>
                <p>Phelan, Peggy. <em>Unmarked the Politics of Performance</em> London: Routledge, 1993.</p>
                <p>Tirohl, Blu. “Now Wash Your Hands: Uncommissioned Art and Gender.” <em>Journal of Gender Studies</em> 25, no. 6 (2016): 693–704. doi:10.1080/09589236.2015.1136205.</p>


        </div>
    </div>
</div>

<div on:click={() => goto(`/five`)} id="click-left" >
	<div class="arrow-left"></div>
</div>

<style>

    a, span {
        text-transform: none;
        display: inline-block;

    }

    #click-left {
        position: fixed;
        bottom: 0;
    }

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

    .subheader {
        font-family: 'Kollektif';
        font-size: 25pt;
    }

    .subsubheader {
        font-family: 'Kollektif';
        font-weight: bold;
        font-size: 15pt;
    }
    

    .info-card {
        color: #24305e;
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

    .bg-overlay {
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

    #context-card {
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

    #info {
        padding: 45px;
    }

    #icons {
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: -27px;
        font-size: 35pt;
    }

    #icons a, span {
        float: left;
        color: #ef473a;
        margin: 4.5px;
    }


</style>