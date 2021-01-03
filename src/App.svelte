<script>
	import Navbar from './Navbar.svelte';
	import Player from './Player.svelte';

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
</script>

<Navbar />
<div class="container">
	{#if players.length === 0}
		<p>No Players</p>
	{:else}
		{#each players as player}
			<Player name={player.name} points={player.points}/>
		{/each}
	{/if}
</div>