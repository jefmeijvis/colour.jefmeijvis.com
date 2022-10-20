<script>
    import { onMount } from "svelte";

    let open = false;
    export let colour;

    onMount(()=>doOnMount())

    function doOnMount()
    {
        setTimeout(()=>open = true, 5000);
    }

    function OnClick()
    {
        open = !open;
    }

</script>


<div 
    class="pull-tab"
    style="bottom:{open?25:0}rem"
    on:click={OnClick}
    on:keypress={OnClick}>
</div>

<div 
    class="menu"
    style="bottom:{open?0:-25}rem">
    <h1>Full screen colour picker</h1>
    <p>Press <b>F11</b> to enter full screen mode</p>
    <p>Pick a colour below</p>
    <input bind:value={colour} type="color"/>
    <p>By <a href="https://www.jefmeijvis.com?ref=colour">www.jefmeijvis.com</a></p>
    <p>Find on <a href="https://github.com/jefmeijvis/colour.jefmeijvis.com">Github</a></p>
</div>


<style>
    a
    {
        text-decoration: none;
        color:black;
    }

    a:hover
    {
        text-decoration: underline;
    }
    h1
    {
        padding-top: .5rem;
        padding-bottom: .5rem;
        color:white;
        background-color: rgb(95, 156, 241);
        margin-bottom: .5rem;
    }
    input
    {
        margin:1rem;
        width : var(--tabWidth);
        height : var(--tabWidth);
        cursor:pointer;
        transition: all ease .5s;
        border:none;
    }

    input:hover
    {
        transform: scale(1.05);
    }

    .menu
    {
        width : var(--menuWidth);
        height : 25rem;
        background-color: white;
        display: block;
        position: absolute;
        transition: all ease .5s;
        left : calc(50% - calc(var(--menuWidth) / 2));
        border-top-left-radius: 1rem;
        border-top-right-radius: 1rem;    
        box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
        text-align: center;
    }

    :root
    {
        --tabWidth : 10rem;
        --menuWidth : 30rem;
    }

    .pull-tab
    {
        
        display: block;
        position: absolute;
        width : var(--tabWidth);
        height : 1rem;
        left : calc(50% - calc(var(--tabWidth) / 2));
        bottom : 0;
        cursor:pointer;
        border-top-left-radius: 2rem;
        border-top-right-radius: 2rem;
        transition: all ease .5s;
        background-color: white;
        box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
    }

    .pull-tab:hover
    {
        height : 2rem;
        border-top-left-radius: 1rem;
        border-top-right-radius: 1rem;
    }
</style>