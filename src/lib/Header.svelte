<script>
    import BurgerMenu from 'svelte-burger-menu';
	import { tick } from "svelte";
	import { goto } from '$app/navigation';

    const preserveScroll = (url) => {
        goto(url, {
            noscroll: true,
        });
    };

</script>

<BurgerMenu>
    <h2 on:click={() => preserveScroll(`/`)}>Home</h2>
    <h2>About</h2>
</BurgerMenu>
