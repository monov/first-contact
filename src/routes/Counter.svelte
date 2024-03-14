<script>
	let count = 0;
	let num;
	const incr = () => {
		num.style.scale = '0';
		setTimeout(() => {
			count++;
			num.style.scale = '1';
		}, 200);
	};
</script>

<h4>Counter shit!</h4>
<h1 class="count-show" bind:this={num}>{count}</h1>
<button class="count-butt" on:click={incr}>Click to count</button>

<style>
	.count-show {
		z-index: 1;
		transition: 0.2s;
		font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
	}

	.count-butt {
		height: 30px;
		width: 100px;
		border: none;
		background: #353535;
		color: #fff;
		border-radius: 10px;
		cursor: pointer;
		transition: 0.2s;
	}
	.count-butt:hover {
		background: #1f1f1f;
	}
	h4 {
		font-family: sans-serif;
	}
</style>
