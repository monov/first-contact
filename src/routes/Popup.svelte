<script>
  import { fade, fly } from "svelte/transition";
	export let isPop;
	function handleExClick() {
		isPop = false;
	}
  //
</script>


{#if isPop}
  <div in:fade={{delay: 50,duration: 200}} out:fade={{delay: 300,duration: 200}} class="pop-body">
    <div in:fly={{delay: 300, duration: 200, y: 500}} out:fly={{delay: 50, duration: 200, y: 500}} class="pop-self">
      <p>This is a popup</p>
      <button class="close-butt" on:click={handleExClick}>Close</button>
    </div>
  </div>
{/if}

<style>
  .pop-self p{
    font-size: 28px;
    font-weight: 400;
  }

  .close-butt{
    height: 30px;
    width: 120px;
    background: rgba(0, 0, 0, 0.925);
    border: solid 2px #000;
    border-radius: 10px;
    color: #fff;
  }

	.pop-self {
		position: relative;
		background: rgba(255, 255, 255, 0.5);
    border: solid 2px rgba(255, 255, 255, 0.438);
		border-radius: 20px;
		height: 200px;
		width: 400px;
    box-shadow: 0 0 10px #1f1f1f;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
    z-index: 10;
    backdrop-filter: blur(20px);
	}

	.pop-body {
		display: flex;
		align-items: center;
		justify-content: center;
		background: rgb(0, 0, 0, 0.5);
		backdrop-filter: blur(10px);
		height: 100%;
		width: 100%;
		position: fixed;
    z-index: 10;
	}

</style>
