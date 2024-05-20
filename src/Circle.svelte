<script>
export let handleClick;
export let x;
export let y;
export let size
export let display
</script>

<main>
    <button class="circle" style="height: {size}px; width: {size}px; left:{x}px; top: {y}px; display: {display};" on:click={handleClick}>
    </button>
</main>

<style>
    .circle{
        position: absolute;
        cursor: pointer;
        display: block;
        height: 150px;
        width: 150px;
        border-radius: 100%;
        background-color: aquamarine;
    }
</style>