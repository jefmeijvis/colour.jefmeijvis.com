<script>
    import Intro from "../lib/intro.svelte";
    import Menu from "../lib/menu.svelte";

    let colour = '#2A6465';
</script>

<svelte:head>
    <title>Colour picker</title>
</svelte:head>

<Intro></Intro>
<div style="background-color:{colour}"></div>
<Menu bind:colour={colour}></Menu>

<style>
    div
    {
        width : 100vw;
        height : 100vh;
        background-color: rgb(71, 165, 248);
    }
</style>