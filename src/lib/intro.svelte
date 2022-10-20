<script>
    import { onMount } from "svelte";
    let open = false;

    onMount(()=>doOnMount())

    function doOnMount()
    {
        open = true;
        setTimeout(()=>open = false, 5000);
    }
</script>


<div style="top:{open ? '10' : '-10'}rem;opacity:{open ? '100' : '0'}%;">
    <h1>Full screen colour picker</h1>
    <p>Select a colour below 🎨</p>
</div>

<style>
    div
    {
        display: block;
        position: absolute;
        color: white;
        text-align: center;
        width: 100%;
        top : 10rem;
        transition: all ease 1s;
    }

    h1
    {
        font-size: 6rem;
    }

    p
    {
        font-size: 3rem;
    }
</style>


