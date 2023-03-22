<script>
	import Button from '$lib/components/Button.svelte';

	function setupGame() {
		let board = [7, 7, 7, 7, 7, 7, 7, 0, 7, 7, 7, 7, 7, 7, 7, 0];

		let p1 = board.slice(0, 8);

		let p2 = board.slice(8, 16);

		let randomPlayer = Number(Math.random() < 0.5 ? 1 : 2);

		return { board, p1, p2, randomPlayer };
	}

	function play() {
		console.log('game started');
		let { board, p1, p2, randomPlayer } = setupGame();
		let boxSelect = prompt(`Player ${randomPlayer} Choose a box from 1 through 7: `, '1');

		if (boxSelect != null) {
			let elementSelect = Number(boxSelect) - 1;
			console.log(elementSelect);
		}
	}
</script>

<h1>Sungka</h1>

<div class="grid-container">
	<div class="item-left">1</div>
	<div class="item2">2</div>
	<div class="item3">3</div>
	<div class="item4">4</div>
	<div class="item5">5</div>
	<div class="item6">6</div>
	<div class="item7">7</div>
	<div class="item8">8</div>
	<div class="item-right">9</div>
	<div class="item10">10</div>
	<div class="item11">11</div>
	<div class="item12">12</div>
	<div class="item13">13</div>
	<div class="item14">14</div>
	<div class="item15">15</div>
	<div class="item">16</div>
</div>

<Button on:click={play}>Start</Button>

<style>
	.grid-container {
		display: grid;
		grid-template-columns: repeat(9, 1fr);
		gap: 10px;
		background-color: #2196f3;
		padding: 10px;
	}

	.grid-container > div {
		background-color: rgba(255, 255, 255, 0.8);
		text-align: center;
		padding: 20px 0;
		font-size: 30px;
	}

	.item-left {
		grid-row: 1 / 3;
		grid-column: 1 / 2;
	}

	.item-right {
		grid-row: 1 / 3;
		grid-column: 9 / 10;
	}
</style>
