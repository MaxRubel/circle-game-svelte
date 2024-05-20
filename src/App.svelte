<script>
// @ts-nocheck

  import Circle from "./Circle.svelte";


let x= 0;
let y= 0;
let size = 0;
let intervalId;
let gameRun = false;

const citcleMoves = () => {
  if(gameRun){
    size = 0
    x = Math.floor(Math.random() * 800) + 1;
    y = Math.floor(Math.random() * 1200) + 1;
    intervalId = setInterval(() => {
    size +=1
  }, 60)
  } else {
      clearInterval(intervalId)
  }
}

const buttonClick = () => {
  gameRun = !gameRun

  if(!gameRun){
    clearInterval(intervalId);
  } else {
    citcleMoves();
  }
}

const handleClick = () => {
  citcleMoves()
}

</script>
 
<main>
  <button on:click={buttonClick}> 
    {#if gameRun}
    STOP
    {:else}
    START
    {/if}
  </button>

  <div class="game-board">
    <Circle {handleClick}{x}{y}{size} display={gameRun ? 'block' : 'none'}/>
  </div>
</main>

<style>
.game-board{
  position: relative;
}
</style>
