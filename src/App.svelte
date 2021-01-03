<script>
	import Navbar from './Navbar.svelte';
	import Player from './Player.svelte';
	import AddPlayer from './AddPlayer.svelte';

	let players = [
		{
			name: "Younhong",
			points: 99
		},
		{
			name: "Yewon Kwon",
			points: 77
		},
		{
			name: "Sumin Lee",
			points: 87
		},
	];

	const addPlayer = (e) => {
		const newPlayer = e.detail;
		players = [...players, newPlayer];
	}

	const removePlayer = (e) => {
		players = players.filter(
			player => player.name !== e.detail)
	}
</script>

<Navbar />
<div class="container">
	<AddPlayer on:addPlayer={addPlayer}/>
	{#if players.length === 0}
		<p>No Players</p>
	{:else}
		{#each players as player}
			<Player name={player.name} points={player.points}
				on:removePlayer={removePlayer}/>
		{/each}
	{/if}
</div>