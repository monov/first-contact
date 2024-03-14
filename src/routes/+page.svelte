<script>
	import Nested from './Nested.svelte';
	import Counter from './Counter.svelte';
	import Popup from './Popup.svelte';
	let name = 'Svelte';
	let isPop = false;
	function openPop() {
		isPop = !isPop;
	}
</script>

<div class="app-body">
	<Popup bind:isPop />
  <section class="svelte">
    <h1>Hello {name.toLocaleUpperCase()}!</h1>
  </section>

  <section class="popopen">
		<button class="popopener" on:click={openPop}>Open the Pop up</button>
	</section>

  <section class="counter">
		<Counter />
	</section>
	
	<section class="p-styled">
		<p>This paragraph is styled</p>
	</section>

  <section>
		<Nested />
	</section>
</div>

<style>
  .popopener{
    height: 30px;
    width: 120px;
    border: none;
    background: #04ff00;
    box-shadow: 0 0 20px #04ff00, 0px 0px 30px #04ff00;
    cursor: pointer;
  }

  .popopen{
    background: rgb(0, 0, 0);
  }

  .app-body{
    height: 100%;
    width: 100%;
  }
  
  .counter{
    background: rgb(14, 255, 155);
  }

  .svelte{
    background: #e35124;
    color: white;
    font-family: sans-serif;
  }

  .p-styled{
    background: #1f1f1f;
  }

	* {
		box-sizing: border-box;
		padding: 0;
		margin: 0;
	}

	p {
		color: goldenrod;
		font-family: 'Courier New', Courier, monospace;
		font-size: 2em;
		font-style: italic;
	}

  section{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 300px;
  }
</style>
